# Research

This repository stores long-form research papers and related artifacts. Each
paper directory should expose a small `metadata.yaml` file so both tools and
people can discover the paper without first parsing the TeX source.

## If You Are Agent

- Start with the paper directory's `metadata.yaml`, then open the TeX entrypoint
  from `artifacts.source_tex`.
- Treat the TeX source as the source of truth; treat the PDF as a build output.
- When a paper makes claims about current code, verify them against the related
  codebase listed in `related_codebases`.
- For `elone`, current implementation-sensitive claims should be checked against
  `/Users/arthur/RustroverProjects/Tondi` before editing wording.
- For `mmr`, consensus and proof structure are primary; if you touch empirical
  numbers, verify them instead of inheriting them blindly.
- Compile into `/tmp/...` rather than polluting the repo with fresh aux files.
- If you add a new paper, create its directory-level `metadata.yaml` and update
  this README in the same change.

## If You Are Human

- Current papers:

| Paper | Directory | Created | Current date | Abstract-level summary |
| --- | --- | --- | --- | --- |
| Elone | `elone/` | 2025-12-17 | 2026-03 | A consensus-embedded payment-channel architecture built around a dual-track UTXO model, native transaction typing, and atomic channel reconfiguration. The current paper snapshot is theory-led but partially backed by code in `Tondi`: consensus tx types, SDK builders, engine/store split, and low-level RPC exist, while PTLC production execution and channel-factory lifecycle remain incomplete. |
| MMR Execution Log | `mmr/` | 2026-01-22 | 2026-01 | A proposal for consensus-level execution-log commitments in GHOSTDAG-based PoW DAG ledgers using Merkle Mountain Ranges. The paper introduces execution-position receipts that prove actual consensus execution order and enable logarithmic verification for historical transactions, bridges, and light clients. |

- Open each paper's `metadata.yaml` first if you want a fast summary, source
  path, build command, and related codebase.
- Main editable sources: `elone/paper.tex` and `mmr/mmr_full_paper.tex`.
- Existing PDFs live beside the TeX sources: `elone/paper.pdf` and
  `mmr/mmr_full_paper.pdf`.
- When you revise a paper, update its metadata if the title, date, status,
  summary, or build entry changes.
