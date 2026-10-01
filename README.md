# b1-skills

Marketplace de plugins de Claude Code para trabajar con SAP Business One (por ahora Service Layer).

Este repo es solo el producto instalable. La fabrica (fuentes, scripts, skills de construccion, evidencias) vive en el repo exterior, que incluye este como submodulo en `b1-skills/`.

## Plugins

- `setup-<sistema>`: prepara `.sbo-b1/<sistema>/`.
- `docs-<sistema>`: documentacion unica para todas las versiones de B1.
- `use-<sistema>`: opera contra el sistema real.

## Instalacion

    /plugin marketplace add <owner>/b1-skills
    /plugin install use-service-layer@b1-skills
