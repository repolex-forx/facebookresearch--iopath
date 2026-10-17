# Repolex Knowledge Graph of facebookresearch/iopath

RDF knowledge graph data for [facebookresearch/iopath](https://github.com/facebookresearch/iopath), parsed by [repolex](https://repolex.ai).

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
rlex download facebookresearch/iopath
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 44f9a451ac092a2b14395e6264b80f0aedfcec1b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 44f9a451ac092a2b14395e6264b80f0aedfcec1b
│           └── chunk-001.nq.gz
├── blob
│   ├── 0abf36d39aa4f53224962acd5837301a166d8a81.nq.gz
│   ├── 0f7ad8bfc173eac554f0b6ef7c684861e8014bbe.nq.gz
│   ├── 10bf6fff55cf85f3509679af57bc1e755e04c9b8.nq.gz
│   ├── 2eb754821692132a99bb5757902984a97369f7f0.nq.gz
│   ├── 4526371b1dac6c580b96d99d4585a496c21d2031.nq.gz
│   ├── 4ccb62fcbf70bad1ad9e4f0bd9909daf713be827.nq.gz
│   ├── 56896c6ac8b3cf062071f4354b2220e29666b64d.nq.gz
│   ├── 5c7f19c6c00a4ac3f2f2bc66f892e44bcbd72612.nq.gz
│   ├── 6165c2792d86d947b2625bac4cee102d7abc2d80.nq.gz
│   ├── 736136bdcfa8c219bea201170a4c1395d6eb0c77.nq.gz
│   ├── 7f0f7113d9cf00add5a247909304ace28487e50b.nq.gz
│   ├── 87370a6d697e3ac136f42ee576ca32e6082cf540.nq.gz
│   ├── 8eee2b47fc204576dc34fce281ceb7f251275672.nq.gz
│   ├── 90b7f89abd01b5593a763cd1ff7d5183de6bd7c6.nq.gz
│   ├── 9185f3c7ccc5f6fa0b7e7ddf94b37441e4f2fa14.nq.gz
│   ├── 96b0c9afa07c568421801bc550c58c91c1fa8c2b.nq.gz
│   ├── 96da85ed00c04da8203e92b8d2886edff2469e3d.nq.gz
│   ├── 9cadec34196bc0d36d5dee44f39d10df41e60a50.nq.gz
│   ├── a6afb7f6851248a452ea1ef066a9095c6141440e.nq.gz
│   ├── a797a19079ea92ba2732c0e366f56bbe74f0f7de.nq.gz
│   ├── ab64967feb71fcd73b39aacce7e1c3c4e9fbf42c.nq.gz
│   ├── b96dcb0480a0b0be0727976e5202a1e7b23edc3f.nq.gz
│   ├── ba8a975987b6dd3adf13213b5390940d1c41a289.nq.gz
│   ├── cd8ccba789e3304b940cf1a93b2f52b737cc7c5d.nq.gz
│   ├── d4216fc7fd7e9b68009a6fea4f0327962585b22e.nq.gz
│   ├── da3ab8261275c58658bc6acf474119313ada5528.nq.gz
│   ├── e5c27dac1cbd1732d53ada79fffbc03b158960d9.nq.gz
│   ├── ea2287512af3098d7e66ecfbb2bf7b455dfad066.nq.gz
│   └── efee016d2193aa0c0c1a921b473e8923c596f55a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 44f9a451ac092a2b14395e6264b80f0aedfcec1b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 37 files
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

[facebookresearch/iopath](https://github.com/facebookresearch/iopath)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
