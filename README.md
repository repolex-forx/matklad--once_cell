# Repolex Knowledge Graph of matklad/once_cell

RDF knowledge graph data for [matklad/once_cell](https://github.com/matklad/once_cell), parsed by [repolex](https://repolex.ai).

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
rlex download matklad/once_cell
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 80fe900b21f6d76c1a2ed74d3343e8a3a88c46d0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 80fe900b21f6d76c1a2ed74d3343e8a3a88c46d0
│           └── chunk-001.nq.gz
├── blob
│   ├── 05115778512af38bba41acc89cea2bc159ad53d4.nq.gz
│   ├── 0c308cab09169eaf7b37e5d0217afd41accd47be.nq.gz
│   ├── 0ccab153cec14c53fa537fa488e90627a2b1514c.nq.gz
│   ├── 0d54f9827ea33e012f5f3cd993b2b64c1eb8815c.nq.gz
│   ├── 124cc3e6d099d46f72e04013ff38de3d6b05893e.nq.gz
│   ├── 1518047460477b6cd2d73256adc4d1bd906903ca.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 18382d8360ad6ecbc436bed927ae09473ee13855.nq.gz
│   ├── 2ac9b53a7dab51e07e040d7546f93592656c16d5.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 3b9e6d20519a904c887d703a06f328cd0900cde8.nq.gz
│   ├── 3cdb19f2a5d34f5de6155e01c890d4cc94d65937.nq.gz
│   ├── 44d70fa0cef0c003c86f00e624076a586d481bd5.nq.gz
│   ├── 4c4c2ea6b8abc3e2dde5a0cabca650e52da0f5da.nq.gz
│   ├── 555d90b60bcc83818c542e32515d0554c11c79c5.nq.gz
│   ├── 69fffdd0f36c5e000c385ab02f797211fba5b4dc.nq.gz
│   ├── 6a998a822c93208b2a88d5868e47e600f7d805a7.nq.gz
│   ├── 6b8d53d144d8014ea810d3c045bb5d0fb2afcbd8.nq.gz
│   ├── 71007de81b9f6787ffb086f3f28aed70e6273f79.nq.gz
│   ├── 852a80494f9558ce82d6935f928ef0c482ffb546.nq.gz
│   ├── 8716f70c26de454ccc512b7be1a8662f267ba119.nq.gz
│   ├── 93bfcedc33c2c47d38cd96f2ce0cfa158cdaf4bc.nq.gz
│   ├── ac9797a96302a5424fff6963b27794063efdaffa.nq.gz
│   ├── af4b5b7d0e7995279be15f9300a7a7982de2afca.nq.gz
│   ├── b8e56ccc6fcd72b4df235a35ebdc520ba60025ad.nq.gz
│   ├── b92b99ac3020cb34d77ecf7cb12cf1932ba631f9.nq.gz
│   ├── be3bcc83f201f882b8d88c09792b227627bed350.nq.gz
│   ├── ca264d25698823bb5c0a23af05f41bc32992ed34.nq.gz
│   ├── d265413f3d3c65274e6d75c8168b6c8aae387b64.nq.gz
│   ├── e591c9c4954965231a059a9da34edc373c75e576.nq.gz
│   ├── e6801258a1e6124846976240cbb629f8548b1d7a.nq.gz
│   ├── e9ff2c16e7de034b47259f85ebb15a9cc9dda899.nq.gz
│   ├── fa44da602450fad9dcdf3316df33c6d00c5dddcd.nq.gz
│   └── ff0d8477be32acff3ec9221705ef14ac87ccf560.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 80fe900b21f6d76c1a2ed74d3343e8a3a88c46d0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[matklad/once_cell](https://github.com/matklad/once_cell)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
