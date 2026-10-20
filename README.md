# Repolex Knowledge Graph of klen/modconfig

RDF knowledge graph data for [klen/modconfig](https://github.com/klen/modconfig), parsed by [repolex](https://repolex.ai).

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
rlex download klen/modconfig
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 646ce7f5a1cb9cb5f22f110e41d750855e1b1039
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 646ce7f5a1cb9cb5f22f110e41d750855e1b1039
│           └── chunk-001.nq.gz
├── blob
│   ├── 20c850c6a393ec7d20a769f5602ead5f785d716d.nq.gz
│   ├── 2247d5f95a7193c7221b9464debe167763b4fae3.nq.gz
│   ├── 271d0271e437660f16f6e89cdbb6d0bc47c8fd06.nq.gz
│   ├── 2f1b9c85cc891b76f911920ccc71fed3adfac82d.nq.gz
│   ├── 4157b6c3f3e7fec81de3937bf2794fa3df8a6271.nq.gz
│   ├── 4a85cc5125bc8c7971d63d2f1ca3068c2b2cec96.nq.gz
│   ├── 5a52a0cfe0789b4f56ea163020a5b00ee8b72f57.nq.gz
│   ├── 6bfd873fe25132760c5d4829469644e029188506.nq.gz
│   ├── a279c4c89a86cb699b4053fff12df667881a2656.nq.gz
│   ├── a515f10ed1e01b6d527e3d9691779e22e932af7d.nq.gz
│   ├── b024da80e9c1c8c800cc1b46e90c1e783cb446cc.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e708ba63246a992cddd84139bac726e3ec42966a.nq.gz
│   ├── f2901722fe90455a68094dcd4b46fad0c44420f1.nq.gz
│   └── fadc6f75ed0093f29ea42f46a31bad73a1051787.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 646ce7f5a1cb9cb5f22f110e41d750855e1b1039.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 22 files
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

[klen/modconfig](https://github.com/klen/modconfig)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
