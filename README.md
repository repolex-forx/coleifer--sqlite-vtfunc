# Repolex Knowledge Graph of coleifer/sqlite-vtfunc

RDF knowledge graph data for [coleifer/sqlite-vtfunc](https://github.com/coleifer/sqlite-vtfunc), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/sqlite-vtfunc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2001b5567bbd83435775efba5457fc0cfdafaa46
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2001b5567bbd83435775efba5457fc0cfdafaa46
│           └── chunk-001.nq.gz
├── blob
│   ├── 050185fcc89217f21adbcc4fd87925aa40157837.nq.gz
│   ├── 06f957a777f089cf0dd7944dd97d5cf9dba8d04d.nq.gz
│   ├── 08c566257665a7ad74240535873392e49d706f03.nq.gz
│   ├── 12e8069a545ac395d7e0caf397164f4d18c43e23.nq.gz
│   ├── 1c87f45eccd0a02017146b7b00fce345fe2c5d25.nq.gz
│   ├── 47ed15a01fe25f6f2b1a33eaeb71626ab142cf58.nq.gz
│   ├── 7e61e19831a725b8b7176cf09d5c599bc74a5b4e.nq.gz
│   ├── 887b60bd40e19396163c1b6c39d9d6157ea0d2b7.nq.gz
│   ├── 8977d7a82960f4e1a705b32a0a9c51cfbaeeda6e.nq.gz
│   ├── c752ab3ead2e7be324e5cafb5e1d53135c16af13.nq.gz
│   ├── d35c13f9ac95d9d88183b19039dcf3e0e7d8f598.nq.gz
│   ├── e0427482b3b174ba7f7c8b407c5f9bd41e443fe4.nq.gz
│   └── f7df426fcda248967ebcf6f25fb8f727828030a3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2001b5567bbd83435775efba5457fc0cfdafaa46.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 20 files
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

[coleifer/sqlite-vtfunc](https://github.com/coleifer/sqlite-vtfunc)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
