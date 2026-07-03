# seagrass_sediment_Analysis_2026

Analysis code for the seagrass marine-sediment study.

Raw data CSVs are deposited on the journal's related site, except for the
public Japan Meteorological Agency data
(https://www.data.jma.go.jp/kaiyou/data/db/kaikyo/series/engan/engan.html)
used for **Fig. 2 / Fig. S7**.

Materials are distributed as zipped folders; each zip contains the input
files and code (Python / R) needed to reproduce the listed figures and
tables.

---

## File map

| Zip | Figures | Tables |
|---|---|---|
| `Fig1_S1_S6.zip` | Fig. 1, Fig. S2–S6 | — |
| `Fig2a_S7.zip` | Fig. 2, Fig. S7 | — |
| `Fig3.zip` | Fig. 3| — |
| `Fig4a_5a.zip` / `Fig4b_5b.zip` | Fig. 4, Fig. 5 | — |
| `Fig6a.zip` / `Fig6b.zip` | Fig. 6a, Fig. 6b | — |
| `Fig6c_S21_S24.zip` | Fig. 7c, Fig. S21–S25 | Table S4, Table S5 |
| `FigS11_S13.zip` | Fig. S11, S12, S13 | Table S1, Table S2 |
| `FigS14.zip` | Fig. S14 | — |
| `FigS15_S16.zip` | Fig. S15, S16 | — |
| `FigS17a.zip` / `Fig17b.zip` | Fig. S17 | — |
| `FigS18.zip` | Fig. S18 | — |
| `FigS19.zip` | Fig. S19 | — |
| `FigS20.zip` | Fig. S20 | — |
| `FigS25.zip` | Fig. S25 | — |

**No code / data (figure itself is the content):
** Fig.8 (conceptual image).
** Fig. S10 (workflow), Fig. S8/S9 photographs (sediment / sampling-method).


---

## Figure legends (current numbering)

**Fig. 1** — Satellite characterisation of seagrass-bearing waters in four Japanese oceanographic regions.
**Fig. 2** — Study regions with seagrass meadows in Japan.
**Fig. 3** — Energy landscape analysis of the symbiotic candidate feature components in marine sediments.
**Fig. 4** — Assessment of the **biome** feature in marine sediments.
**Fig. 5** — Assessment of the **chemical** feature in marine sediments.
**Fig. 6** — Symbolic regression and collective structural equation model of seagrass-sediment holobiont components.
**Fig. 7** — Conceptual model of seagrass sediment holobiont–chemical coupling and coastal ecosystem stability.

**Fig. S1** — Per-site sensitivity analysis controlling for spatial autocorrelation.
**Fig. S2** — Annual comparison of bloom frequency, sediment variability, and SST at satellite-surveyed sites.
**Fig. S3** — Reduced temperature sensitivity of water quality at study sites stratified by CHLA baseline.
**Fig. S4** — Unstratified comparison of temperature sensitivity (necessity of CHLA baseline stratification).
**Fig. S5** — Dissolved organic matter and photosynthetically active radiation at study sites compared with other Japanese coastal sites.
**Fig. S6** — Satellite characterisation of Ariake Bay as a within-region test of the seagrass effect.
**Fig. S7** — Temperature of the adjacent waters surveyed in this study.
**Fig. S8** — The marine sediments surveyed in this study.
**Fig. S9** — Custom sampling methods for sampling in this study.
**Fig. S10** — Workflow for evaluation of biome-chemical network in the study sites.
**Fig. S11** — Symbiotic bacterial diversity in the marine sediment.
**Fig. S12** — Symbiotic eukaryotic diversity in the marine sediment.
**Fig. S13** — NMDS of symbiotic bacterial and eukaryotic diversity.
**Fig. S14** — Relative abundance of bacterial and eukaryotic populations.
**Fig. S15** — Difference-in-differences for symbiotic bacterial families (D_4 level).
**Fig. S16** — Difference-in-differences for symbiotic eukaryotes (D_4 level).
**Fig. S17** — Difference-in-differences for the chemical indices.
**Fig. S18** — dbRDA of seagrass sediment bacterial and eukaryotic communities and their relationships with sediment chemistry.
**Fig. S19** — Feature selection using four machine-learning approaches (AA, Random Forest, XGBoost, LightGBM).
**Fig. S20** — Selection of seagrass sediment feature biome and chemical components based on stochastic symbolic regression.
**Fig. S21** — Filtering of 378,018 candidate SEM models down to 505 universal models reveals diminishing returns of model complexity.
**Fig. S22** — Filter stringency at the SEM enumeration step.
**Fig. S23** — Composition of symbolic regression (SR) pairs across 505 universal SEM models.
**Fig. S24** — Robustness of the holobiont network across fit-criteria stringency.
**Fig. S25** — Profiling of key negative eukaryotes in a collective SEM model.

*(If S8/S9 split differs in the final manuscript, adjust S8–S10 accordingly; the SEM block S21–S25 is fixed as above.)*

---

## Tables

- **Table S1** — α-diversity statistics for the targeted regions.
- **Table S2** — NMDS (β-diversity) statistics for the targeted regions.
- **Table S3** — Pairwise precision-matrix elements: (a) biome network (Fig. 5b); (b) chemical network (Fig. 6b).
- **Table S4** — Symbolic regression formula composition for the SEM pipeline.
- **Table S5** — Variable prevalence and qualified SR pairs from the SEM screening pipeline.

---

## SEM analysis zip — `Fig6c_S21_S24.zip`

**`Code/`**
| Script | Generates |
|---|---|
| `SEM_Figure_505_collective_v10.R` | Fig. 6c (collective SEM architecture) |
| `Fig6c_crossvalidation_summary.R` | Fig. 6c right inset (CV4 / CV8 / LORO AUC, Brier) |
| `phase9_recalc_strict505_final.R` | 697→505 re-filtering (TLI ≥ 0.95 & AGFI ≥ 0.95); writes `phase9_downstream_path_summary_strict505.csv` and `phase9_sr_path_summary_strict505.csv` |
| `Supp_Fig_S21_Figure_k_diminishing_returns_v6_modified.R` | Fig. S21 (378,018→505 filtering, diminishing returns) |
| `Supp_Fig_S22.R` | Fig. S22 (filter stringency) |
| `Supp_Fig_S23_SR_pair_composition.R` | Fig. S23 (SR pair composition) |
| `Supp_Fig_S24.R` | Fig. S24 (robustness across stringency) |

**`Seagrass_SEM_code/`** — SEM pipeline (Stage α/β/γ; phase0–phase6e), unchanged from earlier release.

**`Table_S4_S5_code/`**
| Script | Generates |
|---|---|
| `build_table_s4_pdf.py` | Table S4 (SR formula composition) |
| `build_table_s5_pdf.py` | Table S5 (variable prevalence + 6 qualified SR pairs) |
| `table_style.py` | Shared table-rendering style (imported by both) |

> `build_table_s4_pdf.py` and `build_table_s5_pdf.py` also import data-parsing
> helpers (`load_hall_of_fame`, `build_records`, `BIOME_VARS`, `CHEM_VARS`,
> `PHASE2_GLOB`) from **`build_table_s4.py`** — include this file in the zip as well.

**`Data_file/`**
- `New_seagrass_CLR_region_site_Chem_with_SR.csv`
- `New_seagrass_CLR_region_site_Chem.csv`
- `phase0_sr_equations.csv`
- `phase6e_full_validation_v2.csv`
- `phase7_universal_candidates.csv`  (697 candidates; input to the 697→505 re-filter — do not delete)
- `phase9_downstream_path_summary_strict505.csv`  (505; downstream path values shown in Fig. 6c)
- `phase9_sr_path_summary_strict505.csv`  (505; upstream SR_score1/SR_score2 values, +0.81 / +0.28)
- `S18_scenario_counts.csv`

Plus input CSVs for Tables S4/S5 (place in the same folder as the table scripts):
- `hall_of_fame_<5..10>depth.csv` (biome), `hall_of_fame_depth<5..10>.csv` (chem)
- `phase2_qualified6_pairs.csv`

---

## figshare deposit — `Seagrass_SEM_dataset/`
## 10.6084/m9.figshare.31289155

Large intermediate files (too big for the journal site):
- `phase4_combined_results.csv` (~378,018 rows)
- `phase5c_full_fit.csv` (505-version fit table, 12,651 rows)
- `phase6b_full_path_coefs.csv` (567,651 rows; full path coefficients — source of Fig. 7c / S24 values)
- `phase6d_universality.csv` (12,608 rows)
- `phase6e_full_validation.csv`

---

## Notes on numbering and SR labels

- **697 vs 505**: `phase7_universal_candidates.csv` holds 697 candidates that already satisfy six of the eight fit criteria plus regional universality. `phase9_recalc_strict505_final.R` adds TLI ≥ 0.95 & AGFI ≥ 0.95 to yield the 505 universal models. All main/Supplementary figures and the main text use the 505 version.
- **SR_score labels**: figures, tables, and text use **SR_score1 = biome** and **SR_score2 = chemistry**. Internal data columns use the opposite convention (`.SR1` / `sr1` = chemistry; `.SR2` / `sr2` = biome); the re-label is applied only at display/output (see `internal_lhs` column in `phase9_sr_path_summary_strict505.csv`). Values are unaffected.
- **Source Data**: the `satellite_stats/` CSVs are the Source Data for Fig. 1 and Fig. S3–S6 (BH-adjusted q-values and bin counts included).

---

## Acknowledgement

- Python code: tested with Python 3.10.
- R code: requires the libraries declared at the top of each `.R` file (e.g. `vegan`, `lavaan`, `lightgbm`, `xgboost`, `randomForest`, `arules`).
- Python plots use Helvetica by default and fall back to Arial if unavailable.
- Analysis scripts in this repository were developed with the assistance of Claude (Anthropic). All code was critically reviewed, tested, and validated by H. Miyamoto.
