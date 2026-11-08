# Repolex Knowledge Graph of google-deepmind/mishax

RDF knowledge graph data for [google-deepmind/mishax](https://github.com/google-deepmind/mishax), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/mishax
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1547dfc2caf37f5e006876363d2a0da83dc5f4c0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1547dfc2caf37f5e006876363d2a0da83dc5f4c0
│           └── chunk-001.nq.gz
├── blob
│   ├── 255c5278f0e7d440ea95d888355f15494f262703.nq.gz
│   ├── 439e91a91df4fb1d41645c97ddb3ce7efe984e59.nq.gz
│   ├── 4cf10433e0357b46c30e28020d89fabd94cea610.nq.gz
│   ├── 53ff46a83ebda1d6ea436e79ede0f1b7f5add918.nq.gz
│   ├── 547fe2109112d37d77ab1e83e6ae48e7801039a1.nq.gz
│   ├── 5483dcbeb5fb0bb3b66bc18552bdfd4566b3cb2c.nq.gz
│   ├── 5a4171c657c7c61cbd622be7ae193309efb359e4.nq.gz
│   ├── 5e3c8109dac5dd17fd36e0f4d79cd42011b05c3d.nq.gz
│   ├── 7a4a3ea2424c09fbe48d455aed1eaa94d9124835.nq.gz
│   ├── 7c85b0fa76f5c602c97e5c3ca602f44ed77afe98.nq.gz
│   ├── 7d9ff02bf2f2eaef888c5d055b349ff84ffa1177.nq.gz
│   ├── 87ff772054c0281ecbd43aaf0a6081698c6d510d.nq.gz
│   ├── bf0550f8907309ad85bb1e4833b49e10ae7e04e8.nq.gz
│   ├── cd9e67438825d27338ab9a6bad0831dc0acffa41.nq.gz
│   ├── dcdb413e26c03a4c38193dcf77335ea69be6bb21.nq.gz
│   ├── e2fa5b59a3d01de7ba75050d81a53c0a871c354e.nq.gz
│   └── e60691aab341c0fee68eb837abcbf12e51591266.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1547dfc2caf37f5e006876363d2a0da83dc5f4c0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[google-deepmind/mishax](https://github.com/google-deepmind/mishax)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
