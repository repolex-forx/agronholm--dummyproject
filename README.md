# Repolex Knowledge Graph of agronholm/dummyproject

RDF knowledge graph data for [agronholm/dummyproject](https://github.com/agronholm/dummyproject), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/dummyproject
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 91b440ff13d7bd1dba7ce66cb9cbd51f8adde90d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 91b440ff13d7bd1dba7ce66cb9cbd51f8adde90d
│           └── chunk-001.nq.gz
├── blob
│   ├── 3918ef5bec9948b894e00c4de4781812fc180194.nq.gz
│   └── dab4845ba6066082f49967316f67acb44b5c8f71.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 91b440ff13d7bd1dba7ce66cb9cbd51f8adde90d.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 8 files
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

[agronholm/dummyproject](https://github.com/agronholm/dummyproject)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
