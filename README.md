# Repolex Knowledge Graph of sphinx-contrib/images

RDF knowledge graph data for [sphinx-contrib/images](https://github.com/sphinx-contrib/images), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/images
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fce459ff975a74266f3fbcc3d0850f33d7b09202
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fce459ff975a74266f3fbcc3d0850f33d7b09202
│           └── chunk-001.nq.gz
├── blob
│   ├── 064a62731f4a2beaec9ce828d51ab2c92a8f21a2.nq.gz
│   ├── 12f94c11ed1bbdada2db693de1702275618ec289.nq.gz
│   ├── 2119f51099bf37e4fdb6071dce9f451ea44c62dd.nq.gz
│   ├── 3695495cd97ae1e0410c459ab8d604b72659467f.nq.gz
│   ├── 36bf051e0d54accbe968105f7a7bfc3ff5472246.nq.gz
│   ├── 647baec6fa2bdeee5801dacf9640fe8214fc1231.nq.gz
│   ├── 6b2a8effd7178a6460534b0c33ce8dda16cc0a4e.nq.gz
│   ├── 75a36264a42a0623d8188d510b9f8086805a0a84.nq.gz
│   ├── 78ba6fba108b39af7859ea0e2b5a177347a2a97d.nq.gz
│   ├── 7ca131bb144e22a01efff6ea81fdd8c4602d2fce.nq.gz
│   ├── 85a263219731c78afd8aab16cddcb683eb22587e.nq.gz
│   ├── 91abf22e5cd5ee0d28dbd8571419d875deb3c1f2.nq.gz
│   ├── a07e4e1d3bd5336aee88729532e55c6498591466.nq.gz
│   ├── a17f07aa76a6b94e49b2a9f7633db9ac76f5e6e3.nq.gz
│   ├── afd3133f783ecb09185fabc5f85d3079774ca277.nq.gz
│   ├── b63e1e7f029da571db4c51363e94eda29062f280.nq.gz
│   ├── c4875e484a9436029f1fc34e8e3f85bcba8ba192.nq.gz
│   ├── c538281f33b329affb657261458a2d046194177e.nq.gz
│   ├── d1d9ccddc508ee0a1720a7d70e020cf4ecf872a7.nq.gz
│   ├── d4bb2cbb9eddb1bb1b4f366623044af8e4830919.nq.gz
│   ├── d943b65701ca70a35a47cb8076195591e2c1f71a.nq.gz
│   ├── d9a10c0d8e868ebf8da0b3dc95bb0be634c34bfe.nq.gz
│   ├── ee773f42f1a19eecb810dd44744bdc26453b8408.nq.gz
│   └── f4274afc03ff96eb19b7a8dc6126668145259c54.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fce459ff975a74266f3fbcc3d0850f33d7b09202.nq.gz
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

[sphinx-contrib/images](https://github.com/sphinx-contrib/images)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
