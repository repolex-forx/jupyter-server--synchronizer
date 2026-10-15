# Repolex Knowledge Graph of jupyter-server/synchronizer

RDF knowledge graph data for [jupyter-server/synchronizer](https://github.com/jupyter-server/synchronizer), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter-server/synchronizer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── faa25ac7ba7683021a9026ac9e0512deadd837c8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── faa25ac7ba7683021a9026ac9e0512deadd837c8
│           └── chunk-001.nq.gz
├── blob
│   ├── 174632c7aee095003d064fcc1be2cf9ed70eb2cc.nq.gz
│   ├── 17be720a298692392453785803db1b097507edb8.nq.gz
│   ├── 1856307a2874afc6e671fc279e04fbdd84a6c207.nq.gz
│   ├── 22bcd31c8edcb81e890096815cd0065c21fd533a.nq.gz
│   ├── 396330bb9729d2ec595617aef79fb28600d86bd7.nq.gz
│   ├── 46302b6dc2c370e11d352d7bf2f3a497df9a0c8e.nq.gz
│   ├── 49a709ffe5d222f4b380a102f33ca58a09a31a46.nq.gz
│   ├── 5295e776b63d7adfab3ddad99962cc6f81968909.nq.gz
│   ├── 5474b6810527e148e3e0541fbcdbf0a94c3d257d.nq.gz
│   ├── 60af4c5f16741c7c2fe17cdd9718ae5f6d56d8a4.nq.gz
│   ├── 61e92f54e3074fb2b97db055433119ccbcc4c60c.nq.gz
│   ├── 6540246ca7373ded715ca272f09c36d312c28d02.nq.gz
│   ├── 68bc17f9ff2104a9d7b6777058bb4c343ca72609.nq.gz
│   ├── 6dcaa1311004dc172defa1e32d02dd836f8e7641.nq.gz
│   ├── 6efbb2cac01055d7d7bfefe1112bc7e918b15e0b.nq.gz
│   ├── 725feab5ce652dc39f3f2c77b9fd3c90bf049c65.nq.gz
│   ├── 8342f6411c0ca001376af51705a7adc2f81765a6.nq.gz
│   ├── a6ad7df3545333427c7ebfbdc4f827aed2b848cd.nq.gz
│   ├── b690849b8be8dc29aedd979816ba7805dbc3a68b.nq.gz
│   ├── c96266e3b3e840a80b0bf288485d17b1961c2fd8.nq.gz
│   ├── d0117ec386a75cffdf9c71323dee90acab173430.nq.gz
│   ├── d47dd4b4d484f6419a35fe34f14d1e324a42a471.nq.gz
│   ├── d85a27343f272a44a15734b05904a2da901a4f6e.nq.gz
│   ├── dfe75d82a0a3b6dfa811a626fdfe91151c58cf07.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fcdd3e88b66ec9b10362685146ef2a36088e54f3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── faa25ac7ba7683021a9026ac9e0512deadd837c8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[jupyter-server/synchronizer](https://github.com/jupyter-server/synchronizer)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
