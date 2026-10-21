# Repolex Knowledge Graph of sanic-org/discord-bot

RDF knowledge graph data for [sanic-org/discord-bot](https://github.com/sanic-org/discord-bot), parsed by [repolex](https://repolex.ai).

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
rlex download sanic-org/discord-bot
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2898bfd1e7cc8cecfa5b69f05f3378c8237ef6c8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2898bfd1e7cc8cecfa5b69f05f3378c8237ef6c8
│           └── chunk-001.nq.gz
├── blob
│   ├── 07078a559069849a18c81623dee8fa1fc2cba5a0.nq.gz
│   ├── 07bcb1dd334fa5d1153b720e575b24b28af864ee.nq.gz
│   ├── 453cc0d7672443261c2cee2b15bea79cd10c6821.nq.gz
│   ├── 61a63366751112b951868e894647432e38f2ee93.nq.gz
│   ├── 81d1b6a9f7c038f10bf58104ebc819a2a6a71c8e.nq.gz
│   ├── b3ab099d1908bd336db5d62fc77d34cf90379639.nq.gz
│   ├── dd4b85487e56e0aa8d3753929fa786f45c6a736f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fb5e9583b51b40ab9bfc95b90ba80068d19db328.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2898bfd1e7cc8cecfa5b69f05f3378c8237ef6c8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[sanic-org/discord-bot](https://github.com/sanic-org/discord-bot)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
