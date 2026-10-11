# Repolex Knowledge Graph of pytest-dev/pytest-rerunfailures

RDF knowledge graph data for [pytest-dev/pytest-rerunfailures](https://github.com/pytest-dev/pytest-rerunfailures), parsed by [repolex](https://repolex.ai).

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
rlex download pytest-dev/pytest-rerunfailures
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 01fd226bd533ecd7f6aabe7c155c4ca7bcd8598c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 01fd226bd533ecd7f6aabe7c155c4ca7bcd8598c
│           └── chunk-001.nq.gz
├── blob
│   ├── 0850dc9eacff69d1843a98c3b371cb555d854ef3.nq.gz
│   ├── 1a38eb33f60494487320ee6de8ec8d03a4752846.nq.gz
│   ├── 20944483e0288351aeccc9d39bd499462e47e7d3.nq.gz
│   ├── 220493c368d85bf8ff168b07f0963b142cf87e25.nq.gz
│   ├── 27cdb1a63324dff3b7836ee7456cbd102151f428.nq.gz
│   ├── 28e2db7305dbaf6bc032ed6b1e45d89947f1587e.nq.gz
│   ├── 2c474e0f47f798ebfa21ffcfc7afd294da6e351b.nq.gz
│   ├── 2d7ed43a8b40f8f90c66d1c07f302ee36c8730ff.nq.gz
│   ├── 2ff8820329f2d21cacf08fafe5f79742e8e65462.nq.gz
│   ├── 2ffb7248ed07ee508bf48cdc4992d307121c8c51.nq.gz
│   ├── 31511c664e6b964f18230dd23cb235f497ecb8a6.nq.gz
│   ├── 3c0be12dcd03de768fdffaf155c977c0474e83f9.nq.gz
│   ├── 3f0d0abb313b08a6dce8975370e7f32d65c58d95.nq.gz
│   ├── 4e8a53fafe17f40ed8ced45eeb4e699bd5947c81.nq.gz
│   ├── 6ef7bcb5d77cf19547953de8b5c878731a3770c2.nq.gz
│   ├── 8322209ef979c6e68d256f816588f14966167ba6.nq.gz
│   ├── 87b645b5885cde08e08be2866c980c384613dafc.nq.gz
│   ├── 8a92778bc0b15296a6f7391cf7f060339c6e6be3.nq.gz
│   ├── 8dabb2f5609aa19f6aa6e2105e2c2150691beb3c.nq.gz
│   ├── 9f0ce8c67f3cbddb399ebf4d51d0d5bcb279837f.nq.gz
│   ├── 9f55e8dc7b4f97d31db794e1b5519756a6bada83.nq.gz
│   ├── ab3f3dd41579d859f9a6c836bdafde70209c6e45.nq.gz
│   ├── b069bbedf17e347b670e753a8d4f3f5f094e012e.nq.gz
│   ├── bd80eb941be57c7e25910402f67ed82ea6b6acdd.nq.gz
│   ├── c63d69475033df152a5f8b507566a7cf1e073e2e.nq.gz
│   ├── c8623b4d9563d995167b7acffe2c08b5f9b4d01e.nq.gz
│   ├── cbc7a25f204dbbcb992de164d5996f51ab2355d9.nq.gz
│   ├── cfeffa8c95e72231a4684084d1eb7d31f5f01489.nq.gz
│   ├── d7ca7a9e27e8cd9b4cd1daeb1134f6a8a25b3f5d.nq.gz
│   ├── d9e113ec685b92b018297dd2f200341d1fba01f9.nq.gz
│   ├── da323ef11c5b61a6db0c8459546418fe928aa284.nq.gz
│   ├── db3974acf40f894fd734a917b1a44ecc670359fd.nq.gz
│   ├── dd9533e22996b6b240d0eb51b26c9ac8929e37a5.nq.gz
│   ├── e34e4d97ea87706242fc02a327c1590f93805a4f.nq.gz
│   └── f0198caedb904ea350215045b3031d22cd9d30aa.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 01fd226bd533ecd7f6aabe7c155c4ca7bcd8598c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 43 files
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

[pytest-dev/pytest-rerunfailures](https://github.com/pytest-dev/pytest-rerunfailures)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
