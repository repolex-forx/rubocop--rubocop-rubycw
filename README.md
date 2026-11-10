# Repolex Knowledge Graph of rubocop/rubocop-rubycw

RDF knowledge graph data for [rubocop/rubocop-rubycw](https://github.com/rubocop/rubocop-rubycw), parsed by [repolex](https://repolex.ai).

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
rlex download rubocop/rubocop-rubycw
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ac73b642d617cafe0dda40c20dc53e87e2890e5a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ac73b642d617cafe0dda40c20dc53e87e2890e5a
│           └── chunk-001.nq.gz
├── blob
│   ├── 01266e0caa409a25049790b909774799cb9bcc33.nq.gz
│   ├── 29b049d53263218499a54bb89ede2746640ec2b1.nq.gz
│   ├── 32327520aab3545b3664bf61ad270ef9bae98f83.nq.gz
│   ├── 34c5164d9b56c7d528f061c97f2d2fe02c834bdd.nq.gz
│   ├── 4485842511c770b270c5534497d802f9b866000f.nq.gz
│   ├── 45ed29f96d08b24fccbb3d2a5a6a82c1ee821505.nq.gz
│   ├── 519bad97e0902dc764d0e1d38fc5ebf742b1550b.nq.gz
│   ├── 68439ef0ffa6cdc5914159359fbe1396c1bd34e7.nq.gz
│   ├── 72d17bfcd425b772c841519fd7e3f8650a95a341.nq.gz
│   ├── 75d6ef431096ea1b9dd42100d60e99c1aaa0140e.nq.gz
│   ├── 7851199406128c01879cfd2b00c5f89d632955d0.nq.gz
│   ├── 91e47bd382a69143edc372fe2e8caad354453de2.nq.gz
│   ├── 9f5fc9cb08b14c312077d535d5c490327e54c2ef.nq.gz
│   ├── a7e3cb51e85ba3c11d16270a41deb28aaaabeded.nq.gz
│   ├── a8159182090204db464bd3fcab5f39c03c841c0a.nq.gz
│   ├── b635516c831e6c44ea641ecd01bef945597e7895.nq.gz
│   ├── b67a59501c4709215b86d1a14dfcd54210267954.nq.gz
│   ├── be548be846b2c0dbcdf2146d5c873675c6087b11.nq.gz
│   ├── dc96cb90785b150acb2bfb3ed96da142dfbe2553.nq.gz
│   ├── dce67d860af47a4eb630117ce03624bae45dcf26.nq.gz
│   └── e8f3b15234af3623b983f4847a3c8fad15d51ad3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ac73b642d617cafe0dda40c20dc53e87e2890e5a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[rubocop/rubocop-rubycw](https://github.com/rubocop/rubocop-rubycw)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
