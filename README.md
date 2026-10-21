# Repolex Knowledge Graph of shapely/shapely-rfc

RDF knowledge graph data for [shapely/shapely-rfc](https://github.com/shapely/shapely-rfc), parsed by [repolex](https://repolex.ai).

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
rlex download shapely/shapely-rfc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0946328ec1c72e235d7562ddb151bfbe0acc3763
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0946328ec1c72e235d7562ddb151bfbe0acc3763
│           └── chunk-001.nq.gz
├── blob
│   ├── 01b8644f13ac92f9cd22e9d4e3a81a731d47884b.nq.gz
│   ├── 44567f4b3426d0c3359ac3efee65b6f1b6767291.nq.gz
│   ├── 9f8eb877018d4198aa51aa0c7754aa1a86e6b95d.nq.gz
│   ├── bec311f1779a122fee455f7c0903faee35847864.nq.gz
│   └── d88235366ecba712307184b549a87b12523cccb4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0946328ec1c72e235d7562ddb151bfbe0acc3763.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 13 files
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

[shapely/shapely-rfc](https://github.com/shapely/shapely-rfc)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
