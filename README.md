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
