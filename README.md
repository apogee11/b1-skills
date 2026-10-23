<div align="center">

  # sbo-skills

  **Skills that let AI agents work with SAP Business One: Service Layer, SQL administration and official documentation, with credentials kept away from the agent**

  [![Node 20+](https://img.shields.io/badge/Node.js-20%2B-339933)](https://nodejs.org/)
  [![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

  [Why](#why) | [How it works](#how-it-works) | [Requirements](#requirements) | [Getting started](#getting-started) | [Skills](#skills) | [Subcommands](#subcommands) | [The .sbo-skills folder](#the-sbo-skills-folder) | [Troubleshooting](#troubleshooting)
</div>

<br>

A set of small, explicit skills for AI agents that need to read data from a real SAP Business One Service Layer, change it safely, and look up how the Service Layer and the Business One server behave.

## Why

Working against a live ERP is hard. Pasting passwords into a chat, letting an agent guess entity names, or having it fire a `POST` at production on its own are all ways to have a very bad day. These skills fix the usual failure modes:

- **The agent never sees your credentials.** You type the URL, company, user and password into a local file yourself. The tool logs in on its own, so `Login` and `Logout` are not even requestable.
- **The agent does not guess entities and fields.** It reads an object context (standard and `U_*` fields, types, valid values) and an entity index built from *your* environment.
- **The agent does not change data without asking.** Every call that is not a read is a dry run: it shows the exact method, URL, headers and body, and only a second call with `--execute` sends it. On `prod`, writes also need `--allow-prod`.
- **The agent does not answer from memory.** Questions about the Service Layer or the Administrator's Guide are answered from a reference distilled from the official documentation.

## How it works

The skills are a **distillation of the official SAP Business One documentation** (the Service Layer guide v1.29, plus the Administrator's Guide for Microsoft SQL Server, 10.0 up to FP 2608), organised so an agent can reach the single page that answers a question instead of reading hundreds of pages. Where the documentation is silent, the skill says so instead of filling the gap.

For live systems, a small Node.js tool (`use.mjs`) talks to the Service Layer. Records never enter the conversation: they are written to a local folder with one file per record and an `_index.json`, and the agent only receives the path and a summary.

### Version gates

The Service Layer reference describes **FP 2608**; the minimum supported version is **FP 2208**. The version you declare during setup decides which sections the agent may use:

| Section | Available from |
|---|---|
| Everything else in the Service Layer reference | FP 2208 |
| Webhooks (subscriptions, notifications, messenger, event catalog, configuration) | FP 2602 |
| Webhook formulas (`FilterExpr`) | FP 2608 |

The SQL administration guide covers one edition (10.0 up to FP 2608) and has no version gate. Which entities and fields exist is never taken from the reference: it comes from your server, through the object context.

## Requirements

- **Node.js 20 or later**.
- A SAP Business One Service Layer reachable from your machine (for the Service Layer skills only; the SQL guide needs no system).

## Getting started

### 1. Install

In the root of your project:

```bash
npx skills@latest add apogee11/sbo-skills
```

Pick your agent and take the skills you need. Each skill carries its own `scripts/` folder, so none depends on the others being there. Update later with `npx skills update`.

### 2. Run the setup

Ask your agent to set up Service Layer (skill `sbo-skills-service-layer-setup`). It is a conversation, one question at a time:

1. The agent asks for the language (English or Spanish), the SAP Business One version, the OData version (`v1` is OData V3, `v2` is OData V4; `v2` is proposed from FP 2405) and which environments you want (`dev`, `uat`, `prod`; at least one).
2. It creates `.sbo-skills/service-layer/` with the configuration and one `credentials.json` per environment, with example values, and adds `.sbo-skills/` to your `.gitignore`.
3. **You** open each `credentials.json` and replace the example values with the Service Layer URL, company database, user and password. The agent never asks for these and never opens the file.
4. The agent tests every login and builds an index of the entities each environment exposes.

Run the setup again at any time to start from scratch, or use `sbo-skills-service-layer-add-environment` to add one more environment without losing the rest.

### 3. Use it

Just ask. For example:

> *"How many business partners are there in dev?"*
> *"Show me the first 5 open sales orders of customer C20000 in uat."*
> *"Close order 5 in dev."*
> *"What does a 412 on PATCH mean and how do I use If-Match?"*

Writes look like this:

```
use.mjs request POST "Orders(5)/Close" --entorno dev             # dry run: shows the request, sends nothing
use.mjs request POST "Orders(5)/Close" --entorno dev --execute   # after you approve
```

## Skills

| Skill | What it does | Needs setup |
|---|---|---|
| [`sbo-skills-service-layer`](./skills/sbo-skills-service-layer/SKILL.md) | The one you use day to day. Answers how the Service Layer behaves from the reference ([docs](./skills/sbo-skills-service-layer/docs/index.md)) and operates against a configured environment ([use.md](./skills/sbo-skills-service-layer/use.md)). | Yes |
| [`sbo-skills-service-layer-setup`](./skills/sbo-skills-service-layer-setup/SKILL.md) | Configures the connection: language, SAP Business One version, OData version, environments, and a login test. | No |
| [`sbo-skills-service-layer-add-environment`](./skills/sbo-skills-service-layer-add-environment/SKILL.md) | Adds `dev`, `uat` or `prod` to an existing setup. | Yes |
| [`sbo-skills-admin-guide-sql`](./skills/sbo-skills-admin-guide-sql/SKILL.md) | Administrator's Guide, edition for Microsoft SQL Server: installing, upgrading, configuring services, databases, security, troubleshooting. Documentation only, connects to nothing ([docs](./skills/sbo-skills-admin-guide-sql/docs/index.md)). | No |

## Subcommands

These are the commands of `skills/sbo-skills-service-layer/scripts/use.mjs`, run from your project root (the skill does it for you). Every answer is short JSON with `ok`, `status`, `resumen` and, on failure, `error`. With several environments configured, add `--entorno dev|uat|prod`.

| Command | Does |
|---|---|
| `get <EntitySet> <key>` | One record. A string key made only of digits is quoted: `'123'`. |
| `page <EntitySet> [--top N] [--skip N]` | One page (20 rows by default). |
| `traverse <EntitySet> [--max-rows N]` | Follows `nextLink` up to the cap (1000 by default). |
| `count <EntitySet>` | Only the number of rows. |
| `context <EntitySet> [--refresh]` | The object context of an entity: standard and user fields, types, valid values. |
| `entities [--refresh]` | Where the entity index is (standard and user-defined entities). |
| `request <METHOD> <path> [...]` | Any call: `--header`, `--body`, `--body-file`, `--file`, `--stream-file`, `--read`, `--execute`, `--allow-prod`. Covers CRUD, actions, `$batch`, stored SQL queries (`SQLQueries`) and attachment or image upload and download. |
| `clean <id or path>` | Deletes a dump folder. |

`get`, `page` and `traverse` accept `--filter`, `--select`, `--orderby` and `--expand`. Stored SQL queries are run through `request`, for example `request POST "SQLQueries('open_orders')/List" --read`.

The setup tool (`sbo-skills-service-layer-setup/scripts/setup.mjs`) has its own flags:

| Flag | Does |
|---|---|
| `--init` | Creates the configuration (with `--b1`, `--odata`, `--language`, `--envs`). |
| `--add-env <env>` | Adds one environment. |
| `--verify` | Tests every login and builds the entity index. |
| `--status` | Shows the configured versions and environments, never credentials. |

> [!WARNING]
> Attachment and image upload and download are covered by unit tests only; they were not run end to end against a live Service Layer.

## The .sbo-skills folder

Setup creates `.sbo-skills/service-layer/` in your project and adds `.sbo-skills/` to `.gitignore`. It holds everything local to your systems:

| Path | Contains | Used for |
|---|---|---|
| `config.md` | Language, SAP Business One version, OData version. No secrets. | Choosing which reference sections apply and which OData version the tool calls. |
| `<env>/credentials.json` | Service Layer URL, company database, user and password, in plain text. | Logging in. Edited by you; the agent does not read it. |
| `<env>/session.json` | The current Service Layer session. | Reusing the login between calls. |
| `<env>/context/<Entity>.md` | Object context: fields, types, valid values. | Building correct bodies and `$select`. |
| `<env>/entities-standard.md`, `entities-user.md` | Entities the environment exposes, standard and user-defined. | Checking entity names. |
| `<env>/data/` | Dumps of read results: one file per record plus `_index.json`. | Keeping big answers out of the conversation. Removed by `clean`. |

> [!NOTE]
> The password stays in plain text in `credentials.json`, ignored by git. Anyone who can read your project folder can read it. Keeping it out of the conversation relies on the skill's rules: nothing technical stops an agent's tools from opening that file.

## Troubleshooting

| You see | Do |
|---|---|
| `SETUP_MISSING`, `ENVIRONMENT_NOT_CONFIGURED` | Run the setup (again) and check that the example values in the environment's `credentials.json` were replaced. |
| `ENTITY_NOT_FOUND` | The name is wrong or the entity is not exposed. Read the entity index and retry with the right name. |
| `PROD_WRITE_NOT_ALLOWED` | A write on `prod` without `--allow-prod`. Approve the production write explicitly if you mean it. |
| `HEADER_RESERVED` | `Cookie`, `Host` and `Content-Length` belong to the tool. |
| `FILE_TOO_LARGE`, `FILE_FORBIDDEN` | File over 50 MB, or one of the setup's own files. |
| `Property 'X' of 'Y' is invalid` | The object context may be out of date; run `context <Entity> --refresh`. |
| `Filename too long` or `ENOENT ... mkdir` while installing | Windows paths over 260 characters. Install from a shorter path, or enable long paths (`git config --global core.longpaths true` and Windows "Enable Win32 long paths"), then run the install again. |
| Any Service Layer error with a status | Reported literally: its code and message are the Service Layer's own. |

### Good to know

- The certificate of the Service Layer is never validated (they are usually self-signed): work from a network you trust.
- When the dumps of an environment pass 50 MB the tool deletes the oldest ones, never one under 1 hour old.
- `skills/` is generated from a separate source repository; do not edit it here. Only this `README.md` is written by hand.

## License

[MIT](LICENSE)
