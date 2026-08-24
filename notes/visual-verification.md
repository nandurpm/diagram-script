# Local visual verification

The standalone HTML output at `http://127.0.0.1:4076` rendered the voltage-check example as a readable vertical flow: `START`, `voltage`, and `voltage > 240`, then separate `YES` and `NO` branch paths to `WARNING` and `NORMAL` outcomes, followed by a distinct `END` node.

The same output displayed the matching Mermaid representation with labelled `YES` and `NO` edges. Parser tests also confirmed AST generation, branch labels, source-location errors, and SVG/HTML/Mermaid rendering.
