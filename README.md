# Repolex Knowledge Graph of celery/cookiecutter-celeryproject

RDF knowledge graph data for [celery/cookiecutter-celeryproject](https://github.com/celery/cookiecutter-celeryproject), parsed by [repolex](https://repolex.ai).

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
rlex download celery/cookiecutter-celeryproject
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9efa7bd14701ee18c7a37ac649775e5b7a06577f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9efa7bd14701ee18c7a37ac649775e5b7a06577f
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f9b959049fa116b40e383ee7f6afcab3c0bfc26.nq.gz
│   ├── 0fa8ca31c81d10e84958fa1f724b170ef70121af.nq.gz
│   ├── 1747d11d85698f6eb10fc93437793906573d06ab.nq.gz
│   ├── 18a86aeb40c6a2ac6b225a72178348cf9770fc32.nq.gz
│   ├── 22fb1f902a9f8dced0c3180ed0187471396cbf8b.nq.gz
│   ├── 252ce50a07be06461f0164d9edb50a85cc444ba6.nq.gz
│   ├── 296a1a1b9cf74f6f250b956802918bf83fd1398c.nq.gz
│   ├── 328f49d4821aae5e7e67ad5237c69320a18c18e8.nq.gz
│   ├── 35a4a4823ba566ffb80c0888a64bc35a25186722.nq.gz
│   ├── 3a06053904d7e23ad9fe1a93a0697b26f5df474e.nq.gz
│   ├── 3a472bc836c30415445def35bc58338a1cbe38c5.nq.gz
│   ├── 3f05628255a9939606ed7426e91be18d07581d23.nq.gz
│   ├── 445fcc47081aa587e95569715102cf4bcc0df269.nq.gz
│   ├── 49dcc0ca78d2c2c5a123cc9a04c3216024e71710.nq.gz
│   ├── 5b20da335b1980be7deed652749d4959d650f59b.nq.gz
│   ├── 5d7e07856ac7948f6d8082e236f0843688ea4446.nq.gz
│   ├── 5e4f6b8a841d314ced8eeb3866b05644a2a2f24a.nq.gz
│   ├── 629ee4732cf1cf93d726a3f3b8a27110e796cc95.nq.gz
│   ├── 671a03615d154c12b85b54032226eea4d4d2213c.nq.gz
│   ├── 6795fc6b73deb49f773bc3a3091697b8eba6c11b.nq.gz
│   ├── 70efe73700c5691dfe663f9503a548bdb8371583.nq.gz
│   ├── 740da24644ace5ee9786953ba5cb5ee8d4a17891.nq.gz
│   ├── 8677155029ca200cfa6bbab09f2fda1e33940e3c.nq.gz
│   ├── 956493ceed8c58efd437b711e59001a2f5aca4d0.nq.gz
│   ├── a75aa4e2866fbb962847b820983d264b108d9a7c.nq.gz
│   ├── ad4458238c60a97eaf36288f2f5b3bd2690b8c89.nq.gz
│   ├── badffed09513491ef00c6e9fb7784fb999f3f991.nq.gz
│   ├── bd76e5b9a6f864ffd718e4149c67941abd7f897b.nq.gz
│   ├── be88fdc27be61b3fd34061b2dc8e170db48fa35c.nq.gz
│   ├── c5a3c02758a91d52651efcfcb656d4b5d465d9b6.nq.gz
│   ├── d5624b41deb52207ea2e476a07212dbf5a69531e.nq.gz
│   ├── d6e37dcbf982ccb0715058c592d544cc178911b4.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eae2b24cc1cb46f3e2144109b091a9b80f8a06e8.nq.gz
│   ├── ec7255250fe90f5d7f3442b7c1a35c84cc50cc3d.nq.gz
│   ├── ef39a5dfe7fb80671fddde5d14e4c28a25fe1119.nq.gz
│   ├── f0e19d2dc7a9bc523b71b7ed981d4f9cf465a155.nq.gz
│   └── f16149fc5e59d95aed603e8cd1d1f486c723ef69.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9efa7bd14701ee18c7a37ac649775e5b7a06577f.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 45 files
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

[celery/cookiecutter-celeryproject](https://github.com/celery/cookiecutter-celeryproject)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
