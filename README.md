# evidenceos-neurofusion

> NeuroFusion — multimodal neuroimaging + biomarker fusion platform for TBI outcome prediction. Public methodology, model cards, and integration reference for research partners.

## Status

Active research development. NeuroFusion Phase 1 targets CENTER-TBI and TBICare dataset integration.

## What's here

- `methodology/` — Multimodal fusion architecture (CT + MRI + biomarkers + EHR + time-series)
- `model-cards/` — Model cards for each published NeuroFusion model (TRIPOD+AI compliant)
- `reproducibility/` — Reproducibility scripts and synthetic data examples
- `configs/` — Example multiverse analysis configs (BC-000 to BC-127 biomarker combinations)

## What NeuroFusion does

NeuroFusion integrates six clinical data modalities for TBI outcome prediction:

1. **Structural neuroimaging** (CT, MRI) — processed via MONAI; Marshall + Rotterdam scale extraction
2. **Blood biomarkers** (GFAP, UCH-L1, S100B, NSE, NfL, tau, IL-6) — 128 combinatorial combos (BC-000 to BC-127)
3. **Clinical trajectory** (GCS serial, pupillary response, vital signs) — 6-hour interval time-series
4. **Structured EHR** (demographics, mechanism, comorbidities)
5. **ICP monitoring** (TIL score, daily ICP burden — T2/T3 facilities only)
6. **Functional outcome** (GOSE at 3, 6, 12 months)

The multiverse analysis engine (`evidenceos-research/evidenceos-multiverse`) runs ~25,000 valid analytical cells across 8 axes to characterize how model performance varies with analytical choices — generating Coverage Vibration of Effects (CVoE) as a novel model stability metric.

## Novel contributions

- **CVoE (Coverage Vibration of Effects):** first metric to quantify conformal coverage instability across analytical multiverse
- **SAFE Set:** Rashomon(ε) ∩ Coverage-Valid(δ) — the clinically deployable intersection of near-optimal and coverage-guaranteed models
- **Assay harmonization axis:** explicit correction for Simoa vs Abbott i-STAT biomarker platform differences

## Contributing

Research contributions welcome from neuroimaging and biomarker scientists. All contributions must pass TRIPOD+AI reporting standards and include a model card. See `CONTRIBUTING.md`.

## License

- Methodology documentation: CC-BY-4.0
- Reproducibility scripts: MIT
- Model weights: model-specific (see individual model cards)

## Maintainer

EvidenceOS Research Lab — [`research@evidenceos.com`](mailto:research@evidenceos.com)

## Related repos

- [`multiverse-analysis-toolkit`](../multiverse-analysis-toolkit) — Multiverse analysis framework
- [`cbim-framework`](../cbim-framework) — Patient classification ontology
- [`evidence-capsules`](../evidence-capsules) — Output Evidence Capsule schema
