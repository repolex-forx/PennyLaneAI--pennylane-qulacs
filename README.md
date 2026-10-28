# Repolex Knowledge Graph of PennyLaneAI/pennylane-qulacs

RDF knowledge graph data for [PennyLaneAI/pennylane-qulacs](https://github.com/PennyLaneAI/pennylane-qulacs), parsed by [repolex](https://repolex.ai).

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
rlex download PennyLaneAI/pennylane-qulacs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 654594bd3fe47047980dd5c276641aec58753bf8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 654594bd3fe47047980dd5c276641aec58753bf8
│           └── chunk-001.nq.gz
├── blob
│   ├── 04f88871fb2d765b4d16fceb4c9c513a14d388af.nq.gz
│   ├── 054de48bee6a4331206f702250ea63e40509ee53.nq.gz
│   ├── 096d150ac41bdcfc0595d9afda02db0e78d11a72.nq.gz
│   ├── 10bd335a4522daf891e05f12f05910ad58a69d91.nq.gz
│   ├── 110c475ab644f4c2e939f5274b38329b3c2641a2.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2ad508a2b3acb619d064608d6fee05eb9ff1ce18.nq.gz
│   ├── 3c62c0030e730a84f7c40b1c6fd0ab0fab31133f.nq.gz
│   ├── 4c6e02bcf4f0e3c82e8f172db8de89493a9ccc4a.nq.gz
│   ├── 50a48d859b6e4f6654e9aae33fa980ef78816534.nq.gz
│   ├── 555f16875903296c3059f93cbc3c26b8df526425.nq.gz
│   ├── 5a9406bc68b4577eb06096cf5091d9ae3a04890f.nq.gz
│   ├── 5acd75762c3d37c4a474e5e2c32f913d49b58da1.nq.gz
│   ├── 6ad2f3c6b1dff84a2ab1d6224f0e70943afb1ee8.nq.gz
│   ├── 6f9e005b8c172b734d433f5eb753ec45a8206de5.nq.gz
│   ├── 72970390f9ee61b3e41fdc4d6d8afef12140865e.nq.gz
│   ├── 734dc40efffbdeae9dd2e9f1856ec4d32812535f.nq.gz
│   ├── 801e7fb56692d3d088041471c99444d8bc03094a.nq.gz
│   ├── 83a1f5059534b712d86574f921a0f286a6148c43.nq.gz
│   ├── 8e4de25d73516ab58173e97ed12150fc5281ec63.nq.gz
│   ├── a17f549908319440e0055fffe985a3405ce7d379.nq.gz
│   ├── af5ec1d035e1b1ec73142f45ead248168f60be23.nq.gz
│   ├── b416115124c01b5374cdba39d7522d188aa210b4.nq.gz
│   ├── b5a98b134edd9d94581eb6f3ebc190e52406b486.nq.gz
│   ├── bfeb5e27c235f77ff6c9c2d31fd2cf7fffa1c1a4.nq.gz
│   ├── c1abf5ce880a2cf740a44abc033326098d8524f3.nq.gz
│   ├── ce2de6c0d77d34d6b711a73d7ac5c95086ff4f37.nq.gz
│   ├── cf510d1b3ccda19d64692a87b998b1b0b134747a.nq.gz
│   ├── d9a259015802350bb2e9b9ea963b8b95cc1d61f8.nq.gz
│   ├── d9a5355b552372fba13dc4f7e37e30593e213b9d.nq.gz
│   ├── db0ec8c19908c476b3fbd13c42dbd24ee2ae9c47.nq.gz
│   ├── e1f58966fcc6d6e0c04eea33ce0bc03fe1f1ab59.nq.gz
│   ├── e3efd4f783b179b92d71afa97284896fda077b37.nq.gz
│   ├── ee6e4efeba739c6805b2789315994cba3c13fe27.nq.gz
│   ├── ee7fe4589af9db8ed1c1c361137263958ba71936.nq.gz
│   ├── f67bec815653a41d9d6bb7cda75b00f728640fe0.nq.gz
│   ├── faef2966cb85db130fd5b7cc066e14d94bc7aab2.nq.gz
│   └── ff9e89430f53bd5eba308f846c206f1ca086c72a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 654594bd3fe47047980dd5c276641aec58753bf8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[PennyLaneAI/pennylane-qulacs](https://github.com/PennyLaneAI/pennylane-qulacs)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
