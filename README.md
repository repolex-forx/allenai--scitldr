# Repolex Knowledge Graph of allenai/scitldr

RDF knowledge graph data for [allenai/scitldr](https://github.com/allenai/scitldr), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/scitldr
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5ccad9c00a60ad75c9e04abf7f27d0f53f983b20
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5ccad9c00a60ad75c9e04abf7f27d0f53f983b20
│           └── chunk-001.nq.gz
├── blob
│   ├── 026b17ac59e9815f4ba7ddef9ce95bad61245915.nq.gz
│   ├── 1fab324f8e7ecc2d31eec428ab137d8a6dba7ce3.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 27d5c8b01dfa96aa9065a3be489161748c882637.nq.gz
│   ├── 2cf9409d9acc69a9e672b28cbd6cea2001233dba.nq.gz
│   ├── 3453da2a9e0e0e9f65d518b396f9ccedece56e01.nq.gz
│   ├── 367653bfea867e1d60f20dad6251ff598db80c63.nq.gz
│   ├── 397b52b90fe2677a3837cff885e8d2664514e342.nq.gz
│   ├── 407d7cf158808d3383393af0478ec64e926943c2.nq.gz
│   ├── 522a96172f3cfc942f0693992fb06c8c71c23a32.nq.gz
│   ├── 611984857813644247c98a1ad44a33e8295f712c.nq.gz
│   ├── 63fb01c2bd3dc052bde9b57de74081c1aa007e64.nq.gz
│   ├── 64731a2924dc309514a2e01e0c1a1022be8a95c4.nq.gz
│   ├── 6fc0231950bde1336cccc4066550ad05e8960d79.nq.gz
│   ├── 8c3b35555a2d3aac2ef575bdc2a56fd0fa17b540.nq.gz
│   ├── 8c5a0df3ed262495408e6aeb72cc279e42d649cd.nq.gz
│   ├── 917966acfe6af0265f898399b073299a88d671be.nq.gz
│   ├── 924471ee731a560b0c582531a581a220ba99ae9c.nq.gz
│   ├── 9700e723611c1ad3bbd0eed236cf3a660688423c.nq.gz
│   ├── ade2ff6d71086631583a20e8df0c64328a59752c.nq.gz
│   ├── ae3d11fb3faa8222522d42a2be9391816f6edd67.nq.gz
│   ├── b3c7115fb93aa80e3825cc94ac5749accdf2f5ef.nq.gz
│   ├── bc21185d9cab7b9360b92ea52dcbcbf7931f2625.nq.gz
│   ├── d10931e7bf9212fda85a1b3844f404ed6bfab257.nq.gz
│   ├── dd59586c811a195253149d5640e7b615201281fc.nq.gz
│   ├── e942c3284688623574c1c7369ff632f836a176c6.nq.gz
│   ├── ec3c407dc91b4a8343de56871a209ce2c9bb544f.nq.gz
│   ├── ed1bfef727b320fc54c573e68be07f3e7da59e97.nq.gz
│   ├── f0240c210f73b2731f6b6258d103a2131c812633.nq.gz
│   └── f0dd6a650acac037be4bb08b391327015a73100d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5ccad9c00a60ad75c9e04abf7f27d0f53f983b20.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 38 files
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

[allenai/scitldr](https://github.com/allenai/scitldr)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
