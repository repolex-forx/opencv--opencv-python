# Repolex Knowledge Graph of opencv/opencv-python

RDF knowledge graph data for [opencv/opencv-python](https://github.com/opencv/opencv-python), parsed by [repolex](https://repolex.ai).

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
rlex download opencv/opencv-python
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 031876bd46b781b8f4db2075327e5a78a53dff63
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 031876bd46b781b8f4db2075327e5a78a53dff63
│           └── chunk-001.nq.gz
├── blob
│   ├── 046cf7f9e3c67285620b263caf5e55bb8eed29c3.nq.gz
│   ├── 07ac1259cda13c62bde69335a647b824454fc282.nq.gz
│   ├── 13e8003c4071e3e4887a37ce2c99a36a7794f25d.nq.gz
│   ├── 15079e07fcd59f8a55f584b13b45c09ac063509d.nq.gz
│   ├── 178fd6ec188c2f950183582f26f0359f10bdaf36.nq.gz
│   ├── 1cad2750a50da66bc344a874d527c5452a24d5b1.nq.gz
│   ├── 2761baea0b13e56ab584a300790180c60badbf5f.nq.gz
│   ├── 328bf50632a988cf1cc494d557936d84fec16335.nq.gz
│   ├── 3e55aa834f64c72c0beb7ab5646c0044519437d9.nq.gz
│   ├── 42e714463e24b7d62201d707312b7d9c3638f70a.nq.gz
│   ├── 4714f2f4d55098cb31ecf39e0a28fe98ac6272d4.nq.gz
│   ├── 587a42bfacd8401281a51fe5dbc8ea44f4e156d5.nq.gz
│   ├── 6411ff3902a688f635940bf4c2e139b287301170.nq.gz
│   ├── 6be3b68a8e03666c09af0174239472b5b13db566.nq.gz
│   ├── 6e00e8f3e4d37680d96d621813a6c1e1a74bfdf0.nq.gz
│   ├── 7193d3b9cdb4750875d9b10728c31c9bd189c0e1.nq.gz
│   ├── 7504f4b2b7cb46ae16afffe073fe8f8b20b51e81.nq.gz
│   ├── 7914668911efef61212dbe0b010e6a801e6356e1.nq.gz
│   ├── 7fc8413858d909cb8c8e2e9dd1d6db2f9e242344.nq.gz
│   ├── 89144a4156f344e65c70474dfb3958817af5f3e4.nq.gz
│   ├── 8bec5deea09fa66ca790fe7cc93df8ae071e987c.nq.gz
│   ├── 96b7dd520291ef5719df36fddb53a6d914e30ead.nq.gz
│   ├── 9a56d6424191dfef1c9f9728121f159e6b6ceded.nq.gz
│   ├── 9e646fe818c8b14e669857f0e3c539441e52bebf.nq.gz
│   ├── a38920180c29cf689611f6a16bd3fec5227bb1bd.nq.gz
│   ├── a3f5287f1d800d5eef5c7c1ac70c80346c6bb73a.nq.gz
│   ├── ab42b5c45d086148634e9dfb003659fa516053f1.nq.gz
│   ├── b396ab55c3b8757527144924ee78cb6aa5ce36be.nq.gz
│   ├── c4d47bc792267f4a21b9012a2a003a933f513481.nq.gz
│   ├── c52bfe3432bbd5e97d27e48866dfe524c2859b9c.nq.gz
│   ├── cb9a7e7bc9359d7e5643ca60f42b1dda78e3f286.nq.gz
│   ├── cffc998ca90a4edfc1952bb0d98caf12c9758f6d.nq.gz
│   ├── e2a1ffc74b2a4b44cbf7aefc413db86199209940.nq.gz
│   ├── e5c83d8318896f2f61f5f5a0d86ad6fb4f01d2ef.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed139d6d50cc43f89c27392621f20d174d0bf051.nq.gz
│   ├── efb20a4ca8852cbbea34f6ff00442f7cddfe8a07.nq.gz
│   ├── f20080ae286f7169c910addc16fe313b01a2d8eb.nq.gz
│   ├── f7cdee49c2f887b50968d76144a21c86b78e0e23.nq.gz
│   └── ff65d776331c99bf660bc6923d9cf028964cfe9b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 031876bd46b781b8f4db2075327e5a78a53dff63.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 48 files
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

[opencv/opencv-python](https://github.com/opencv/opencv-python)

---
*Parsed on 2026-11-02 by [repolex](https://repolex.ai)*
