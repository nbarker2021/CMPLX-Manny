# CMPLX-Manny

Unified hosting root for the **MannyAI / CQE-CMPLX** active development ecology.

This repository is a **submodule umbrella** (monorepo-unify planned once both
subtrees reach work-completion). Each component is an independent, private GitHub
repo tracked here as a git submodule.

## Structure

| Path | Repo | Role |
|------|------|------|
| `cqekernel/` | `nbarker2021/cqekernel` | Stdlib-only CQE/CMPLX kernel (lattice / forge / reforge systems). Ships precached `cqekernel.db`. Installable: `pip install cqe-kernel`. This is the default kernel package — when NOT inside MannyAI dev, install it as a Python lib. |
| `MannyAI/` | `nbarker2021/MannyAI` | The MannyAI form: agents, CEM, corpus, MCP, plugins, benchmarks. Active dev. |
| `PaperEcology/` | `nbarker2021/Paper-Ecology` | The 240-paper LCR system + C1–C8, W1–W8, appendix, plus the DerivationLedger proof pipeline. Active dev. |

## Claim-derivation status (PaperEcology)

The 240-paper open-claim system was run through the **DerivationLedger** pipeline
(`PaperEcology/ProofLib/DerivationLedger/`). Result: **347 proof receipts, all
`derived_D`** (data-backed with computational receipt). Sources: in-corpus PDFs,
the 415k-crystal `CrystalLib` store, published papers (e.g. arXiv:1603.06518 for
24D kissing optimality), and internal LCR derivations. No open claims remain
unresolved; 4 partials closed via real provenance + computational checks.

## Working with submodules

```bash
git clone --recurse-submodules https://github.com/nbarker2021/CMPLX-Manny.git
# or after clone:
git submodule update --init --recursive
```

Update a component:
```bash
cd MannyAI && git pull origin main && cd ..
git add MannyAI && git commit -m "bump MannyAI"
```

## Data policy

- Heavy binaries (CrystalLib DB, arXiv PDFs, runtime `*.db`) are **not** versioned
  in the submodules — they are referenced by path / precached by `cqekernel` /
  manifest. Kernel precaches all lattice/forge/reforge data.
- Stale/analysis-snapshot documentation is **demoted locally** (kept on disk,
  outside hosted folders) per the workspace AI constitution — not tracked.

## Status

- Private. Sole IP holder: CQE-CMPLX-1T.
- Snapshot date: 2026-07-08.
- All three submodules pushed clean (0 secrets, 0 DB/PDF tracked).
