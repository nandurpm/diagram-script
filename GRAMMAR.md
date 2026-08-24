# Diagram Script grammar

Diagram Script intentionally has a small line-oriented grammar so students and engineers can write a readable technical flow without a visual editor.

```ebnf
diagram      = "START", newline, { statement, newline }, "END" ;
statement    = arrow, ( read | check | branch | operation ) ;
arrow        = "->" ;
read         = "READ", whitespace, text ;
check        = "CHECK", whitespace, text ;
branch       = label, ":", whitespace, text ;
operation    = text ;
label        = letter, { letter | digit | space | "_" | "-" } ;
text         = non-empty text ;
```

Comments start with `#` or `//`. A `CHECK` must be followed by one or more labelled branches. Branches become outcome nodes and each reconnects to `END` in the initial language version.

```text
START
  -> READ voltage
  -> CHECK voltage > 240
  -> YES: WARNING
  -> NO: NORMAL
END
```

The parser reports line and column information for invalid lines, missing boundaries, branches without a preceding `CHECK`, and checks without branches. Use `diagram-script parse` to inspect the AST, `validate` to confirm a file, and `render` for `svg`, `html`, or `mermaid` output.
