# Repolex Knowledge Graph of py-pdf/PyPDF-Builder

RDF knowledge graph data for [py-pdf/PyPDF-Builder](https://github.com/py-pdf/PyPDF-Builder), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download py-pdf/PyPDF-Builder
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5dce41b09a1b9c43bfb6f102876a4915a7f42afb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5dce41b09a1b9c43bfb6f102876a4915a7f42afb
│           └── chunk-001.nq.gz
├── blob
│   ├── 2413620fe64ba5ffb939f95620b88179a7acacbd.nq.gz
│   ├── 25b62901bc2a5ab709122f12868495f389c0945f.nq.gz
│   ├── 2aa3b1c8fb503709994283658ec9c8612a5d87db.nq.gz
│   ├── 41719e5db54c3e070c75c87d0cd3af64fb2e5a12.nq.gz
│   ├── 49b7c547883ca209bf5c2e4b65196af6ce93f7ed.nq.gz
│   ├── 57be8324f2db1e6eef1ff0f06449caf3fd2e82fa.nq.gz
│   ├── 88da84e98f22fc800a427f5d13d262595de7165a.nq.gz
│   ├── 8e33dc0b8cb2c62f7229bafc4442f1f987525d0a.nq.gz
│   ├── a98765d7e5e34d220ce44db9ccd0f6d03d5f7521.nq.gz
│   ├── afc873c840b74ae46cad889dc197e53d73a6a66d.nq.gz
│   ├── c2895509e41040702f01f5e3cbb4a9413f461201.nq.gz
│   ├── d1f125772373bad6646c4d5c9e85f349a4af1812.nq.gz
│   └── d525522e4455cefb08edb6641543cdaab679e071.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5dce41b09a1b9c43bfb6f102876a4915a7f42afb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[py-pdf/PyPDF-Builder](https://github.com/py-pdf/PyPDF-Builder)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
