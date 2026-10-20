# Repolex Knowledge Graph of tox-dev/tox-pipenv

RDF knowledge graph data for [tox-dev/tox-pipenv](https://github.com/tox-dev/tox-pipenv), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/tox-pipenv
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fd9e3946b2f1e8dddf0585fc8582937f84fd9fcc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fd9e3946b2f1e8dddf0585fc8582937f84fd9fcc
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b87b3003b56f66f3e42495ee8cdb44314387b05.nq.gz
│   ├── 1cc86c8b52f9281a3fd5576e3ec641e5cd887a0e.nq.gz
│   ├── 1e06782b2cd52e0dda134cc7bb51a345488cef42.nq.gz
│   ├── 22565d7dcf11a4a58bebe2ddf45627a4615fa75b.nq.gz
│   ├── 3370cbd08cd688fdb985bec5174a46aef9775fcb.nq.gz
│   ├── 361135c9f303b9dac9322038fa12d9e1bd6a7e91.nq.gz
│   ├── 3c6b09425e21f73e50087b39286cc0207c4782b2.nq.gz
│   ├── 58f2604788469aa3a2eabb5eee51a80fcaa736e7.nq.gz
│   ├── 591752f38317477b6460315de6c127a4b445944c.nq.gz
│   ├── 5dad9aa3634f8d09b8dffdbf73e5ba30647e2766.nq.gz
│   ├── 679a410e146fc774cff13900d8f10d4f99136c2a.nq.gz
│   ├── 775321b89eb5356857bea4d3564d9d51a8518d09.nq.gz
│   ├── 8567e171a8dcd7945dee0cfd2a7cbeac2ad50e9a.nq.gz
│   ├── 9a80d2a63c5d5a92b91d8a56ef14de5505b6cb2f.nq.gz
│   ├── 9eb30e6ed2e25c479f175840151948a2e27a0cd0.nq.gz
│   ├── a0865bba63666c02a557e25c77db89df5645ca4d.nq.gz
│   ├── b2ad60ca6cd406165a6700d28c335dce438dea9a.nq.gz
│   ├── b538190c021ea5864aec9fe896eb0113769361a0.nq.gz
│   ├── bb1e631c4cd9c6db0db3f7bfb663a19e44738c7f.nq.gz
│   ├── c062218737a8c343602d5c79046518cc75e7ff8b.nq.gz
│   ├── c44d37cc7a63d7fcf2658ab8847f2ffd6bb13e61.nq.gz
│   ├── ceef7eda54baf51508e33d2ec5ec21c225bfc6fe.nq.gz
│   ├── e4de8a1e92cd3e0dc282048266241aab0c02c695.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fd9e3946b2f1e8dddf0585fc8582937f84fd9fcc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[tox-dev/tox-pipenv](https://github.com/tox-dev/tox-pipenv)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
