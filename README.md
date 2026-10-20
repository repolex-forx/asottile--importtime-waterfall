# Repolex Knowledge Graph of asottile/importtime-waterfall

RDF knowledge graph data for [asottile/importtime-waterfall](https://github.com/asottile/importtime-waterfall), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/importtime-waterfall
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── dbe92da0660592b6d12a49fee4da41c48d61308f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── dbe92da0660592b6d12a49fee4da41c48d61308f
│           └── chunk-001.nq.gz
├── blob
│   ├── 29d09f8b97b7cf08f6022d37e64a89ce88f1e8de.nq.gz
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 3fdffa121e3b0e62264cdf10bc360c93537670b7.nq.gz
│   ├── 43f3bfe16306a0af7ebe1544cc5c050f492c9a1b.nq.gz
│   ├── 6a581d61107450a11a858edb40a654fcf8a19afb.nq.gz
│   ├── b7af5ef213084fe100c5bb755659ef68c14dae5b.nq.gz
│   ├── c7073597394899039ddc7ff7d54642b40547cc23.nq.gz
│   ├── ca1d90ea180858ae143c0e62d920e350d3acc62d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e99a9ab7e2bfdf95f909c767afe01c341866deb5.nq.gz
│   └── ec3b537984ef3420b5d1002f4525306cc7d46a1b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── dbe92da0660592b6d12a49fee4da41c48d61308f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[asottile/importtime-waterfall](https://github.com/asottile/importtime-waterfall)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
