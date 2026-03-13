# Research

This repository stores long-form research papers and related artifacts. Each
paper directory should expose a small `metadata.yaml` file so both tools and
people can discover the paper without first parsing the TeX source.

## If You Are Agent

- Start with the paper directory's `metadata.yaml`, then open the TeX entrypoint
  from `artifacts.source_tex`.
- If `artifacts.compiled_pdf` exists, treat it as the preferred reading copy
  for quick review, but still treat the TeX source as the source of truth.
- When a paper makes claims about current code, verify them against the related
  codebase listed in `related_codebases`.
- For `elone`, current implementation-sensitive claims should be checked against
  `/Users/arthur/RustroverProjects/Tondi` before editing wording.
- For `mmr`, consensus and proof structure are primary; if you touch empirical
  numbers, verify them instead of inheriting them blindly.
- Compile into `/tmp/...` rather than polluting the repo with fresh aux files.
- If you are asked to publish a repository PDF, copy only the final PDF back
  into the paper directory under a formal title-derived filename and record it
  in `metadata.yaml`.
- If you add a new paper, create its directory-level `metadata.yaml` and update
  this README in the same change.
- If you rename or add a published PDF, keep the README paper table aligned with
  `artifacts.compiled_pdf`.

## If You Are Human

- Current papers:

| Paper | Directory | Preferred PDF | Created | Current date | Abstract-level summary |
| --- | --- | --- | --- | --- | --- |
| Elone | `elone/` | `Elone Yellow Paper.pdf` | 2025-12-17 | 2026-03 | A consensus-embedded payment-channel architecture built around a dual-track UTXO model, native transaction typing, and atomic channel reconfiguration. The current paper snapshot is theory-led but partially backed by code in `Tondi`: consensus tx types, SDK builders, engine/store split, and low-level RPC exist, while PTLC production execution and channel-factory lifecycle remain incomplete. |
| MMR Execution Log | `mmr/` | `Logarithmic Execution-Log Commitments.pdf` | 2026-01-22 | 2026-01 | A proposal for consensus-level execution-log commitments in GHOSTDAG-based PoW DAG ledgers using Merkle Mountain Ranges. The paper introduces execution-position receipts that prove actual consensus execution order and enable logarithmic verification for historical transactions, bridges, and light clients. |
| Elone Prism | `elone_merkle/` | `elone_merkle/Elone_Prism_Proof_First_Merkleized_Channels.pdf` | 2026-03-13 | 2026-03 | A dedicated Elone paper derived from the March 2026 Merkle design memorandum. It now reads as a formalized protocol-design draft: proof-first merkleized channels with explicit partition assignment, deterministic settlement calculus, a state-package recovery object, and a defined benchmark agenda for the remaining systems questions. |

- Open each paper's `metadata.yaml` first if you want a fast summary, source
  path, preferred PDF, build command, and related codebase.
- Main editable sources: `elone/paper.tex`, `mmr/mmr_full_paper.tex`, and
  `elone_merkle/paper.tex`.
- Preferred reading PDFs currently exist for `elone`, `mmr`, and
  `elone_merkle`.
- When you revise a paper, update its metadata if the title, date, status,
  summary, preferred PDF, or build entry changes.
