# Diagram Script

**Diagram Script** is a small, offline DSL for technical flowcharts and block diagrams. It provides a lexer, parser, AST, branch-aware validator, meaningful syntax errors, SVG/HTML/Mermaid renderers, CLI, examples, and grammar documentation.

> **Scope:** Diagram Script represents the logic you write; it does not verify engineering correctness, safety, or completeness. Review diagrams against approved procedures and system documentation before operational use.

## Example

```text
START
  -> READ voltage
  -> CHECK voltage > 240
  -> YES: WARNING
  -> NO: NORMAL
END
```

| Output | What it provides |
|---|---|
| AST JSON | Parsed node, branch, line, and edge structure. |
| SVG | Self-contained offline visual flowchart. |
| HTML | Standalone rendered diagram with a Mermaid export section. |
| Mermaid | Text for tools that support Mermaid flowcharts. |

## Local Linux and Windows use

Install **Node.js 22+** and pnpm. This is a portable local tool, not a hosted service or native installer, and has no public website URL.

| Task | Linux / macOS shell | Windows PowerShell or Command Prompt |
|---|---|---|
| Parse AST | `./run-local.sh parse examples/voltage-check.diagram` | `run-local.cmd parse examples\voltage-check.diagram` |
| Validate | `./run-local.sh validate examples/voltage-check.diagram` | `run-local.cmd validate examples\voltage-check.diagram` |
| Render standalone HTML | `./run-local.sh render examples/voltage-check.diagram --format html --out reports/demo/voltage-check.html` | `run-local.cmd render examples\voltage-check.diagram --format html --out reports\demo\voltage-check.html` |
| Serve output locally | `./run-local.sh serve reports/demo/voltage-check.html --port=4075` | `run-local.cmd serve reports\demo\voltage-check.html --port=4075` |

The preview server binds only to `127.0.0.1`.

## Validation

```bash
pnpm install
pnpm test
pnpm check
pnpm demo
```

Tests cover valid parsing, YES/NO branches, labels, invalid syntax, AST output, and all renderers.

## License

MIT.

## Live Render Demo

A responsive, synthetic/demo report is available at [https://diagram-script.onrender.com](https://diagram-script.onrender.com). The hosted view is read-only and preserves the repository's documented local-first boundaries.

<!-- render-live-url:https://diagram-script.onrender.com -->

<!-- clear-use-guide -->
## Clear use guide

### Install

Use Node.js 22 or newer, clone this repository, and install its dependencies:

```bash
git clone https://github.com/nandurpm/diagram-script.git
cd diagram-script
pnpm install
```

### Open it locally

Start the local web/report server:

```bash
pnpm start
```

Then open the URL printed by the terminal. The production report hosts use http://localhost:4080 unless a different PORT value is set. To choose another port, use PORT=5050 pnpm start on Linux/macOS or set PORT=5050 && pnpm start in Windows Command Prompt.


### Use the hosted version

**Live URL:** [https://diagram-script.onrender.com](https://diagram-script.onrender.com)

The hosted version is a browser-friendly report or application view. It runs on Render’s free tier, so the first request after inactivity can take longer while the instance starts.

### Windows and Linux

The same Node.js commands work in Windows PowerShell, Windows Command Prompt, and a Linux terminal. Use the platform-specific port command above only when you need a non-default local port.

### Important scope

This project follows its existing local-first and read-only boundaries. Demo/report content is generated or supplied through the documented local workflow; a hosted page does not provide hidden access to your device, private files, hardware, accounts, or network.

## Project structure

| Path | Responsibility |
|---|---|
| [`examples/`](examples/README.md) | Contains small, reviewable example inputs that demonstrate Diagram Script's supported syntax and workflows. |
| [`notes/`](notes/README.md) | Contains design verification notes and screenshots that support maintainers but are not loaded by the application at runtime. |
| [`src/`](src/README.md) | Contains the production implementation of Diagram Script: command handling, domain rules, storage, reports, and local serving as applicable. |
| [`tests/`](tests/README.md) | Contains automated regression tests for Diagram Script's public behavior and important safety constraints. |

Important root files include `package.json` for supported commands, `run-local.sh` and `run-local.cmd` where present for platform launchers, and this README as the primary developer entry point.

## Documentation map

- [`examples/README.md`](examples/README.md) — Contains small, reviewable example inputs that demonstrate Diagram Script's supported syntax and workflows.
- [`notes/README.md`](notes/README.md) — Contains design verification notes and screenshots that support maintainers but are not loaded by the application at runtime.
- [`src/README.md`](src/README.md) — Contains the production implementation of Diagram Script: command handling, domain rules, storage, reports, and local serving as applicable.
- [`tests/README.md`](tests/README.md) — Contains automated regression tests for Diagram Script's public behavior and important safety constraints.

