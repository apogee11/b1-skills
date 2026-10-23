<div align="center">

  # sbo-skills

  **Skills that let AI agents work with SAP Business One: Service Layer, SQL administration and official documentation, with credentials kept away from the agent**

  [![Node 20+](https://img.shields.io/badge/Node.js-20%2B-339933)](https://nodejs.org/)

  [Requirements](#requirements) | [Getting started](#getting-started) | [Skills](#skills) | [The .sbo-skills folder](#the-sbo-skills-folder)
</div>

<br>

The skills are a **distillation of the official SAP Business One documentation**, organised so an agent can reach the single page that answers a question instead of reading hundreds of pages. Where the documentation is silent, the skill says so instead of filling the gap.

## Requirements

- **Node.js 20 or later**.
- A SAP Business One Service Layer reachable from your machine (not needed for the SQL guide).

## Getting started

Install, in the root of your project:

```bash
npx skills@latest add apogee11/sbo-skills
```

Then ask your agent to set up Service Layer. It asks a few questions, creates the `.sbo-skills/` folder and tells you which `credentials.json` to fill in yourself. The agent never asks for your password. After that, just ask in plain words, for example *"How many business partners are there in dev?"*

## Skills

| Skill | What it does | Needs setup |
|---|---|---|
| [`sbo-skills-service-layer`](./skills/sbo-skills-service-layer/SKILL.md) | Answers how the Service Layer behaves and operates against a configured environment. | Yes |
| [`sbo-skills-service-layer-setup`](./skills/sbo-skills-service-layer-setup/SKILL.md) | Configures the connection and tests the login. | No |
| [`sbo-skills-service-layer-add-environment`](./skills/sbo-skills-service-layer-add-environment/SKILL.md) | Adds `dev`, `uat` or `prod` to an existing setup. | Yes |
| [`sbo-skills-admin-guide-sql`](./skills/sbo-skills-admin-guide-sql/SKILL.md) | Administrator's Guide for Microsoft SQL Server. Documentation only, connects to nothing. | No |

## The .sbo-skills folder

Setup creates `.sbo-skills/service-layer/` in your project and adds it to `.gitignore`. It holds everything local to your systems:

| Path | Contains |
|---|---|
| `config.md` | Language, SAP Business One version and OData version. No secrets. |
| `<env>/credentials.json` | URL, company database, user and password for that environment. Edited by you. |
| `<env>/context/`, `entities-*.md` | Fields and entities your server exposes. |
| `<env>/data/` | Results of reads, kept out of the conversation. |

> [!NOTE]
> The password stays in plain text in `credentials.json`, ignored by git. Anyone who can read your project folder can read it.
