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

- Current paper directories: `elone/` for the payment-channel and
  native-consensus architecture paper, and `mmr/` for the MMR execution-log
  commitment paper for GHOSTDAG-based PoW DAG ledgers.
- Open each paper's `metadata.yaml` first if you want a fast summary, source
  path, build command, and related codebase.
- Main editable sources: `elone/paper.tex` and `mmr/mmr_full_paper.tex`.
- Existing PDFs live beside the TeX sources: `elone/paper.pdf` and
  `mmr/mmr_full_paper.pdf`.
- When you revise a paper, update its metadata if the title, date, status,
  summary, or build entry changes.
