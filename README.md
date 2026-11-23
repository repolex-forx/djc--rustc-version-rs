# Repolex Knowledge Graph of djc/rustc-version-rs

RDF knowledge graph data for [djc/rustc-version-rs](https://github.com/djc/rustc-version-rs), parsed by [repolex](https://repolex.ai).

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
rlex download djc/rustc-version-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── eeca449cca83e24150e46739e797aa82e9142809
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── eeca449cca83e24150e46739e797aa82e9142809.nq.gz
│   └── repolex
│       └── eeca449cca83e24150e46739e797aa82e9142809
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c7c487bc9f94b994bf382cb4ec64ec5b677ec46.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 22d9b57effec56512c54a9d2c018591684b20c07.nq.gz
│   ├── 40b8817a47beba464cd86e3f81260cd41b5e70dd.nq.gz
│   ├── 6a1c4f8b167dca2cce48f6996208b21e84a2676b.nq.gz
│   ├── 90ee18eeb6dc1544f8510934c1db47966170ed42.nq.gz
│   ├── 93a41648a70f65ae560f7d3e2c26448241324f39.nq.gz
│   ├── 9f3f7a5c85d8c175676de419a2cc67e3e7124fa0.nq.gz
│   ├── ab173681c143b4cebdac660f5ec1cb18ee234d67.nq.gz
│   ├── c3cff7048a8df1dc61e30abc34488bf78c089cef.nq.gz
│   └── d14c768a4441fcab0a4b3fab74d0946a73055ddf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── eeca449cca83e24150e46739e797aa82e9142809.nq.gz
├── filetree
│   └── eeca449cca83e24150e46739e797aa82e9142809.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 21 files
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

[djc/rustc-version-rs](https://github.com/djc/rustc-version-rs)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
