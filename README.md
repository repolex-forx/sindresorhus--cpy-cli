# Repolex Knowledge Graph of sindresorhus/cpy-cli

RDF knowledge graph data for [sindresorhus/cpy-cli](https://github.com/sindresorhus/cpy-cli), parsed by [repolex](https://repolex.ai).

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
rlex download sindresorhus/cpy-cli
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 55a03d44e2eb7810b8c33b909d7c07415b9d1095
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 55a03d44e2eb7810b8c33b909d7c07415b9d1095.nq.gz
│   └── repolex
│       └── 55a03d44e2eb7810b8c33b909d7c07415b9d1095
│           └── chunk-001.nq.gz
├── blob
│   ├── 14714b8aa463ac29e13c408ac951ab71db57c073.nq.gz
│   ├── 1c6314a31833395fd5ff016a6506bdd51860657c.nq.gz
│   ├── 239ecff1372358a22aa99dcbb375fdad7abba817.nq.gz
│   ├── 43c97e719a5a824700932f72e6e7e6748ce45d01.nq.gz
│   ├── 5358dc50b2883157fca0fa4a12d2bb18acb093ee.nq.gz
│   ├── 6313b56c57848efce05faa7aa7e901ccfc2886ea.nq.gz
│   ├── 6412b1708d93b0915e53caaa3485e16b16ac3358.nq.gz
│   ├── 6ab9e0a66fe006487ceb0b85a0755c8f5c0bd096.nq.gz
│   ├── b88307856b17e387e66c6f4696e1dc29dbdb4c8d.nq.gz
│   └── fa7ceba3eb4a9657a9db7f3ffca4e4e97a9019de.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 55a03d44e2eb7810b8c33b909d7c07415b9d1095.nq.gz
├── filetree
│   └── 55a03d44e2eb7810b8c33b909d7c07415b9d1095.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 20 files
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

[sindresorhus/cpy-cli](https://github.com/sindresorhus/cpy-cli)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
