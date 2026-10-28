# Repolex Knowledge Graph of Kozea/misfile

RDF knowledge graph data for [Kozea/misfile](https://github.com/Kozea/misfile), parsed by [repolex](https://repolex.ai).

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
rlex download Kozea/misfile
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b2c71b4369efea52216afc23e0a33d12568efb77
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b2c71b4369efea52216afc23e0a33d12568efb77
│           └── chunk-001.nq.gz
├── blob
│   ├── 30593313feb96cb05df6c8173de9323c6b6ce9ab.nq.gz
│   ├── 3e666242bdb66d89603eb61611281e8a202232c9.nq.gz
│   ├── 44810dee745002ae6e3b4713b0e73921f49a7d23.nq.gz
│   ├── 55586e8331a112e3d77df653bb6a41c2aea9bd54.nq.gz
│   ├── 55ae5b6f7ddd7eda58023669a00da2cd05b81663.nq.gz
│   ├── 63f0735cdf7cd738c54633c40a0a01edc2ebe061.nq.gz
│   ├── 66dbcce26627ac7ec82dd549cfe8dd882dca85b0.nq.gz
│   ├── 7c70f295805619a36edd6b2164253dfaf09c74a4.nq.gz
│   ├── 7d1c8129121fa2cf71d7f2107923d325d150d285.nq.gz
│   ├── c9ab9edeaf05003842261d768eefa98511a34874.nq.gz
│   ├── eaf0661fdb43f1626c00323144979a851ebd04af.nq.gz
│   └── ee60132f1c8e9ace826f605ebea5e2053d0ba43e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b2c71b4369efea52216afc23e0a33d12568efb77.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 19 files
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

[Kozea/misfile](https://github.com/Kozea/misfile)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
