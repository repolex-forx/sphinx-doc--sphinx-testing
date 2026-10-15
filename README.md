# Repolex Knowledge Graph of sphinx-doc/sphinx-testing

RDF knowledge graph data for [sphinx-doc/sphinx-testing](https://github.com/sphinx-doc/sphinx-testing), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-doc/sphinx-testing
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 89bdde5cf7b3dc4057f48ea6cb84ee126b7b00b7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 89bdde5cf7b3dc4057f48ea6cb84ee126b7b00b7
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d5f088544d41419c2911b591e78f5626e5e319b.nq.gz
│   ├── 143c61b702ac45ff66d2c5107c13e33b09647114.nq.gz
│   ├── 14fc4d4b285b4a6f1314abb42464fd0ccb160c89.nq.gz
│   ├── 3db938f5c3cf55a7fdfbbc5986d4faa9cc2f2872.nq.gz
│   ├── 42af7835ea03a937e532abe4dd87909b38f9b8b1.nq.gz
│   ├── 431156cda6bb257242c3edec8dc9a950fafa85ec.nq.gz
│   ├── 4a1ef257c76963c9b617774ee7c3e7b714f7688d.nq.gz
│   ├── 4e535fb850c6d74892f3a542a754ba848d69ca07.nq.gz
│   ├── 7b5218f3682f9b654f80f0763639ec4b900751bd.nq.gz
│   ├── 811144f4b37880f679f60ba95996b090cf57aab7.nq.gz
│   ├── 98d800b287e9836d344de696a811d63d5df3f566.nq.gz
│   ├── a8cb276abea5b8b65c60d88d0890ed61df36c249.nq.gz
│   ├── ad7150a18689e938e20a6abe9b1bf66c5d39ac0b.nq.gz
│   ├── bb4476709a6968526ece852ede70ac02053bd7c1.nq.gz
│   ├── ce4f4bf0114d8b1d8e430093ec36db2a9daf442e.nq.gz
│   ├── df34a1a3b184e9a92ea993b6da6b75a41a06ab05.nq.gz
│   ├── e2e4097806e1c35ad9802dbfd7262f240581b3ae.nq.gz
│   ├── f1f173bb84308b5ac59cfc40df20a81136559699.nq.gz
│   ├── f81c30bc4bbe5600999cdb569048c59fe84d96e0.nq.gz
│   └── fda32c1ab65177d7d5169eb8ff35a6d4accde0db.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 89bdde5cf7b3dc4057f48ea6cb84ee126b7b00b7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[sphinx-doc/sphinx-testing](https://github.com/sphinx-doc/sphinx-testing)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
