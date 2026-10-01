# Repolex Knowledge Graph of block/bergr

RDF knowledge graph data for [block/bergr](https://github.com/block/bergr), parsed by [repolex](https://repolex.ai).

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
rlex download block/bergr
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bbe9bf8c4a668fa56ec39a4214e078b52be5ab96
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── bbe9bf8c4a668fa56ec39a4214e078b52be5ab96.nq.gz
│   └── repolex
│       └── bbe9bf8c4a668fa56ec39a4214e078b52be5ab96
│           └── chunk-001.nq.gz
├── blob
│   ├── 0367d2331a2cbfb3dadb43da08affe106a235c28.nq.gz
│   ├── 081cbe83449cf8e625a3e2e79b6b35415c4e1503.nq.gz
│   ├── 08929527091640d0f7d7b7ef64529eae25f035c7.nq.gz
│   ├── 0ba9db25329d0b336e39ca8cde8470c5b7bc45eb.nq.gz
│   ├── 0bcb621b1c2f34cb595e65ceb277ef909c4fedd6.nq.gz
│   ├── 141c2761869a58d20a16ec227ac12898a8298cad.nq.gz
│   ├── 1bc469e68eb776aa52185c6cbfc5cdcaee837ce3.nq.gz
│   ├── 25f0bc5ed80683a81f46e6bfd1cf8ea0b56c6807.nq.gz
│   ├── 2d217b164f0215a1eef0bd683a1246e50937c025.nq.gz
│   ├── 3052574ecbf04058ac9b6af8970da75c901b84e0.nq.gz
│   ├── 30a41bc1f62c39226f42fc9dd99844e22a2b846a.nq.gz
│   ├── 31559b7d115e3c105b328cce9b9dcd9774025061.nq.gz
│   ├── 383f4511d444516caed0fd113ee8a2b640cd2290.nq.gz
│   ├── 39c76dbe09e72ee86cab79f5177a58682f274dc7.nq.gz
│   ├── 451d2edf21ffc58d380d6591f8496d3aa2af2a8b.nq.gz
│   ├── 4601f25a62250896f88ed8b8bde42f02d8b7302e.nq.gz
│   ├── 55666fe77e2b23f30bff7cc5b1dc0a41fa99ec96.nq.gz
│   ├── 6233dd133d8b9c6891968f05cd567ca578f09c4f.nq.gz
│   ├── 672e1be4dec82ebb8a0adecd9f0201a424864461.nq.gz
│   ├── 6ad5776ec6b9508fc7ff283e20ee55cf0c8f2b01.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 77854f790d60b71a83062c55c1a55a75ca72a031.nq.gz
│   ├── 85905036f4cc5b2a614891ac6c784cb751011a57.nq.gz
│   ├── 8d114400d7eda6f0466e73915a90f3e5aaeb2b59.nq.gz
│   ├── 8d13e09403c0018da72d9469f09f496185f92122.nq.gz
│   ├── 9af003564a5dc2e587fadd7b5f5756d6a04008cf.nq.gz
│   ├── a07da83c6392fe5ca9351c75bf900ebec0ba52a6.nq.gz
│   ├── b141b0f1a50d852f155e387dcffbeec2872b3562.nq.gz
│   ├── b753bdb841e7d073c6ae1e3b66eabfb2eb556985.nq.gz
│   ├── c086141a539b29d2324efe1a77078ff79869837f.nq.gz
│   ├── cef7b323796d7161cad095cf4df76d06a3ecd79c.nq.gz
│   ├── e889550ba4cbc92a720527042e5f6e7a303bfcbc.nq.gz
│   ├── eb76a78c1a80fd83d5290fe5ed488c3299c0aa9c.nq.gz
│   ├── ed92975080ec8046e2fb131e2d91049924f84fa2.nq.gz
│   ├── f596a8ed203ec366e266e67b9feba905c73ba778.nq.gz
│   ├── fe28214d3352b0ed40820a4999317694c8b1ef57.nq.gz
│   ├── fe6c350fab1675db967cf5d624c25af809e7e0e9.nq.gz
│   └── fef99e7073e6517488e6327700158aed39ab0e99.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── bbe9bf8c4a668fa56ec39a4214e078b52be5ab96.nq.gz
├── filetree
│   └── bbe9bf8c4a668fa56ec39a4214e078b52be5ab96.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 48 files
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

[block/bergr](https://github.com/block/bergr)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
