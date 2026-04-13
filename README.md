# Repolex Knowledge Graph of ivanovmg/unitofwork

RDF knowledge graph data for [ivanovmg/unitofwork](https://github.com/ivanovmg/unitofwork), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download ivanovmg/unitofwork
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── de53931e7e1a8e5a8f6681fda24c40e241991d46
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── de53931e7e1a8e5a8f6681fda24c40e241991d46.nq.gz
│   └── repolex
│       └── de53931e7e1a8e5a8f6681fda24c40e241991d46
│           └── chunk-001.nq.gz
├── blob
│   ├── 0640d8fb73315d29e0b747861bd4611626add9e4.nq.gz
│   ├── 138750037936fe4221ee256fe120affdce437c1d.nq.gz
│   ├── 17411b2b223ec8693fbf692f59e7713e66b42fc6.nq.gz
│   ├── 20e5d4824db89d2e210ec8fe0538a86d1cac1f46.nq.gz
│   ├── 21a10f570ed572af56fc95d4e3598e434418e828.nq.gz
│   ├── 76d1ef96ff18b602da2d45ca2be31390539d6a98.nq.gz
│   ├── 7906bf70fe26dc6adf0162b3862977c19ce06fd1.nq.gz
│   ├── 8f836457c7d0842c5173b646970a86d2b759a9bb.nq.gz
│   ├── 9ab814a820c8c29b9d31d3959c30635c242d01a3.nq.gz
│   ├── b298a904ce9754b08a21679b89b19b6e5b270911.nq.gz
│   ├── c3083a6eef02ff976dbdf001d7798135a2a7dac0.nq.gz
│   ├── e3f54bd767d7d21ad4fb0964adc1eafe75fa50b6.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fcb2bb8ab37ca22db6dbea1322a3f635ec59e3bb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── de53931e7e1a8e5a8f6681fda24c40e241991d46.nq.gz
├── filetree
│   └── de53931e7e1a8e5a8f6681fda24c40e241991d46.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 24 files
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

## Source repository

[ivanovmg/unitofwork](https://github.com/ivanovmg/unitofwork)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
