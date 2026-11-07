# seagrass_sediment_Analysis_2026

Analysis code for the seagrass marine-sediment study.

Raw paired-end MiSeq reads are deposited at the DNA Data Bank of Japan (DDBJ),
BioProject **PRJDB043178**. The upstream QIIME2 processing (raw reads → ASV
feature tables + taxonomy + diversity) is in **`qiime2_pipeline.zip`**; its
output count tables are the input to the figure/table bundles below. Processed
data CSVs are deposited on the journal's related site, except for the public
Japan Meteorological Agency data
(https://www.data.jma.go.jp/kaiyou/data/db/kaikyo/series/engan/engan.html)
used for **Fig. 2 / Fig. S7**.

Large intermediate files are on figshare (10.6084/m9.figshare.31289155); the
archived release is on Zenodo.

Materials are distributed as zipped folders; each zip contains the input
files and code (Python / R) needed to reproduce the listed figures and
tables.

---

## File map

| Zip | Figures | Tables |
|---|---|---|
| `qiime2_pipeline.zip` | (upstream: reads → ASV tables) | — |
| `Fig1_S1_S6.zip` | Fig. 1, Fig. S1–S6 | — |
| `Fig2_S7.zip` | Fig. 2, Fig. S7 | — |
| `Fig3.zip` | Fig. 3 | — |
| `Fig4a_5a.zip` / `Fig4b_5b.zip` | Fig. 4, Fig. 5 | Table S3 |
| `Fig6a.zip` / `Fig6b.zip` | Fig. 6a, Fig. 6b | — |
| `Fig6c_S21_S25.zip` | Fig. 6c, Fig. S21–S25 | Table S4, Table S5 |
| `TableS6_saiki_sensitivity.zip` | — | Table S6 |
| `TableS7_Desulfobulbaceae_genus.zip` | — | Table S7 |
| `FigS10_S13.zip` | Fig. S11, S12, S13 | Table S1, Table S2 |
| `FigS14.zip` | Fig. S14 | — |
| `FigS15_S16.zip` | Fig. S15, S16 | — |
| `FigS17.zip` | Fig. S17 | — |
| `FigS18a.zip` / `FigS18b.zip` | Fig. S18 | — |
| `FigS19.zip` | Fig. S19 | — |
| `FigS20.zip` | Fig. S20 | — |
| `FigS26.zip` | Fig. S26 | — |

**No code / data (figure itself is the content):**
Fig. 8 (conceptual image); Fig. S10 (workflow); Fig. S8 / S9 photographs
(sediment / sampling-method).

---

## Amplicon-processing pipeline — `qiime2_pipeline.zip`

Reproduces the sequence processing described in the Supplementary Methods
("Detection of bacteria and eukaryotes"; "Bacterial and eukaryotic diversity").

- **QIIME2 2021.4** — import, cutadapt (primer removal), DADA2 (paired-end
  denoise/merge, no length truncation), classify-sklearn (taxonomy).
- **QIIME2 2022.11** — 16S α/β-diversity metrics only.
- Reference: **SILVA 132** (99% OTUs), primer-specific extracted reads;
  **naïve Bayes** classifier.

```
16S/  01 classifier-prep (V3–V4)   02 pipeline (import→cutadapt→DADA2→taxonomy→filter)   03 diversity (depth 5000)
18S/  01 classifier-prep (V4)      02 pipeline                                           03 diversity (depth 50)
sample-metadata.tsv   132 samples — sample-id, Habitat (seagrass/non), Seagrass (1/0), Site, Region (A–D), RegionName
```
Raw reads: DDBJ PRJDB043178. Run order per amplicon: 01 → 02 → 03.

---

## Figure legends (current numbering)

**Fig. 1** — Satellite characterisation of seagrass-bearing waters in four Japanese oceanographic regions.
**Fig. 2** — Study regions with seagrass meadows in Japan.
**Fig. 3** — Energy landscape analysis of seagrass and non-seagrass sediment microbiome communities.
**Fig. 4** — Assessment of the **microbiome** feature in marine sediments.
**Fig. 5** — Assessment of the **chemical** feature in marine sediments.
**Fig. 6** — Symbolic regression and collective structural equation model of seagrass sediment microbiome and chemical features.
**Fig. 7** — Conceptual model of seagrass sediment microbiome–chemistry coupling and coastal ecosystem stability.

**Fig. S1** — Per-site sensitivity analysis controlling for spatial autocorrelation.
**Fig. S2** — Annual comparison of bloom frequency, sediment variability, and SST at satellite-surveyed sites.
**Fig. S3** — Reduced temperature sensitivity of water quality at study sites stratified by CHLA baseline.
**Fig. S4** — Unstratified comparison of temperature sensitivity (necessity of CHLA baseline stratification).
**Fig. S5** — Dissolved organic matter and photosynthetically active radiation at study sites compared with other Japanese coastal sites.
**Fig. S6** — Satellite characterisation of Ariake Bay as a within-region test of the seagrass effect.
**Fig. S7** — Temperature of the adjacent waters surveyed in this study.
**Fig. S8** — The marine sediments surveyed in this study.
**Fig. S9** — Custom sampling methods for sampling in this study.
**Fig. S10** — Workflow for evaluation of microbiome–chemistry coupling in the study sites.
**Fig. S11** — Bacterial diversity in the marine sediment observed in this study.
**Fig. S12** — Eukaryotic diversity in the marine sediment observed in this study.
**Fig. S13** — NMDS of bacterial and eukaryotic diversity in marine sediments.
**Fig. S14** — Relative abundance of bacterial and eukaryotic populations.
**Fig. S15** — Difference-in-differences for bacterial families (D_4 level).
**Fig. S16** — Difference-in-differences for eukaryotes (D_4 level).
**Fig. S17** — Difference-in-differences for the chemical indices.
**Fig. S18** — dbRDA of seagrass sediment bacterial and eukaryotic communities and their relationships with sediment chemistry.
**Fig. S19** — Feature selection using four machine-learning approaches (AA, Random Forest, XGBoost, LightGBM).
**Fig. S20** — Selection of seagrass sediment microbiome and chemical feature components based on stochastic symbolic regression.
**Fig. S21** — Filtering of 378,018 candidate SEM models down to 505 universal models reveals diminishing returns of model complexity.
**Fig. S22** — Filter stringency at the SEM enumeration step.
**Fig. S23** — Composition of symbolic regression (SR) pairs across 505 universal SEM models.
**Fig. S24** — Robustness of the sediment microbiome–chemistry coupling across fit-criteria stringency.
**Fig. S25** — Full collective SEM architecture underlying Fig. 6c.
**Fig. S26** — Profiling of key negative eukaryotes in a collective SEM model.

*(If the S8/S9 split differs in the final manuscript, adjust S8–S10 accordingly; the SEM block S21–S25 is fixed as above.)*

---

## Tables

- **Table S1** — α-diversity statistics for the targeted regions.
- **Table S2** — NMDS (β-diversity) statistics for the targeted regions.
- **Table S3** — Pairwise precision-matrix elements: (a) microbiome network (Fig. 4b); (b) chemical network (Fig. 5b).
- **Table S4** — Symbolic regression formula composition for the SEM pipeline.
- **Table S5** — Variable prevalence and qualified SR pairs from the SEM screening pipeline.
- **Table S6** — Dependence of the four SEM hubs on site representation (site-balance sensitivity: Saiki and Noto balancing), verified in R (lmPerm) and Python (Freedman–Lane).
- **Table S7** — Genus-level (D_5) composition of the family Desulfobulbaceae in seagrass versus non-seagrass sediments (predominant metabolic guild indeterminate from amplicon data).

---

## SEM analysis zip — `Fig6c_S21_S25.zip`

**`Code/`**
| Script | Generates |
|---|---|
| `SEM_Figure_505_collective_v10.R` | Figs. 6c and S25 (collective SEM architecture) |
| `Fig6c_main_simplified (1).R` | Fig. 6c (collective SEM visualization <simple version>) |
| `Supp_Fig_S25_crossvalidation_summary.R` | Figs. 6c and S25 right inset (CV4 / CV8 / LORO AUC, Brier) |
| `phase9_recalc_strict505_final.R` | 697→505 re-filtering (TLI ≥ 0.95 & AGFI ≥ 0.95); writes `phase9_downstream_path_summary_strict505.csv` and `phase9_sr_path_summary_strict505.csv` |
| `Supp_Fig_S21_Figure_k_diminishing_returns_v6_modified.R` | Fig. S21 (378,018→505 filtering, diminishing returns) |
| `Supp_Fig_S22.R` | Fig. S22 (filter stringency) |
| `Supp_Fig_S23_SR_pair_composition.R` | Fig. S23 (SR pair composition) |
| `Supp_Fig_S24.R` | Fig. S24 (robustness across stringency) |
| `Supp_Fig_S25_SEM_505_full_supplementary_name.R` | Fig. S25 (collective SEM visualization) |

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

## Site-balance sensitivity zip — `TableS6_saiki_sensitivity.zip`

Tests whether each of the four SEM downstream hubs (Desulfobulbaceae,
Corallinophycidae, Intramacronucleata, Diatomea) keeps its regional
universality under two site-balance perturbations: (i) complete exclusion of
the Saiki site (non-Saiki pool), and (ii) three independent balanced
resamplings (random seeds 1–3) in which the two over-represented sites —
**Saiki** (24 seagrass / 12 non-seagrass) and **Noto** (12 / 12) — are randomly
reduced to six seagrass and six non-seagrass samples each, yielding a fully
balanced design (6/6 at every one of the eight sites; 96 samples, 24 per
region). A hub is regionally universal when the Seagrass × Region interaction
p ≥ 0.05. The test is run in **two independent implementations** and both are
included.

**Result (`Table_S6_combined.csv` / `.docx`):** Desulfobulbaceae is the only hub
that remains regionally universal under every condition in both implementations;
the eukaryotic hubs are not universal. Cross-regional robustness therefore resides
in the group-level microbiome–chemistry coupling structure, anchored by
Desulfobulbaceae, rather than in any individual taxon.

**Layout** (self-contained per condition; see `code_R/README_HOWTO.md`):
```
code_R/       make_balanced.R, make_non_saiki.R (generators); sem_stage_g_phase6d_{non_saiki,seed1,seed2,seed3}.R; README_HOWTO.md
code_python/  verify_phase6d.py
data/complete_exclusion/  ..._non_saiki.csv (96 rows) + phase6d_non_saiki.R + verify_phase6d_python.csv
data/seed{1,2,3}/         balanced_seed0N.csv + phase5c_full_fit_seedN.csv (pool) + phase6d_seedN.R + verify_phase6d_python.csv
```

**Condition-data generation** from the full dataset
`New_seagrass_CLR_region_site_Chem_with_SR.csv` (132 rows; in `Fig6c_S21_S25.zip`
`Data_file/` and on figshare; site codes `X8 = Saiki`, `X2 = Noto`):
- `make_non_saiki.R` → non-Saiki pool (`Site != X8` → 96 rows)
- `make_balanced.R 1|2|3` → `balanced_seed01/02/03.csv` (Saiki X8 and Noto X2 → 6/6)

**R implementation** (`lmPerm::aovp`, 999 permutations):
`sem_stage_g_phase6d_{non_saiki,seed1,seed2,seed3}.R`, run inside each condition folder.

**Independent Python cross-check** (`verify_phase6d.py`, Freedman–Lane, 4,999 permutations):
```
python3.10 verify_phase6d.py <condition_folder>   # writes verify_phase6d_python.csv
```
It needs only the condition data (no model pool) and reproduces the four-hub
interaction p-values directly.

**Model pools.** The balanced-condition pools (`phase5c_full_fit_seed1/2/3.csv`)
are included in each `seed*/` folder; the complete-exclusion pool
(`phase5c_full_fit_non_saiki.csv`, ~5 MB) is on the figshare deposit. The pool is
required only for the full phase6d run (model counts 186 / 452 / 1830 / 75), not
for the per-hub interaction p-values themselves.

**Note on the two implementations.** The exact p-values for the eukaryotic hubs
differ between lmPerm and Freedman–Lane because these taxa are near-absent
(near-zero variance) in one or more regions (e.g. Corallinophycidae in the
Sea-of-Japan region), which makes the interaction sum-of-squares sensitive to the
permutation scheme. The implementation-independent conclusions — Desulfobulbaceae
universal under all conditions, the eukaryotic hubs not — hold in both.

**Pool filter (AGFI).** The phase6d pool filter uses gfi>=0.95, agfi>=0.90,
wrmr<=1.0; the AGFI threshold (0.90) is relaxed relative to the main-text criterion
(0.95) because sub-sampling reduces sample size — this is a sensitivity analysis,
not the primary model selection.

---

## Desulfobulbaceae genus-level zip — `TableS7_Desulfobulbaceae_genus.zip`

Decomposes the family Desulfobulbaceae (the bacterial SEM hub, Fig. 6c) into its
genus-level (D_5, SILVA 132) members, to test whether a sulfide-oxidising
cable-bacteria genus could account for the family-level enrichment.

**Result (`TableS7_Desulfobulbaceae_genus.csv` / `.docx`):** the family is enriched
in seagrass sediment (6.232% vs 5.334%; log2 +0.225; MWU p = 0.0345), but 88.8% of
that signal comes from unresolved members (uncultured + unassigned), and every named
genus with a significant difference is lower in seagrass — including the
sulfur-disproportionating *Desulfurivibrio* (q = 0.019). The cable-bacteria genus
*Candidatus* Electrothrix is detected in only 5 of 132 samples (one region; p = 0.243)
and, without extraction/PCR negative controls, is not usable as evidence. The
predominant metabolic guild within Desulfobulbaceae therefore cannot be determined
from these amplicon data, and remains an open question.

**`Code/`**
| Script | Generates |
|---|---|
| `build_table_s7_desulfobulbaceae_genus.py` | Table S7 (genus-level composition + Mann–Whitney/BH tests) |

```
python3.10 build_table_s7_desulfobulbaceae_genus.py
# writes Table_S7_Desulfobulbaceae_genus.csv
```

**`Data_file/`** — `Bacteria_seagrass_D5_genus.csv` (132 samples × genus-level 16S,
QIIME2 D_0..D_5 taxonomy), `Seagrass_list_cnd_dex250917.csv` (sample metadata:
name, dex, env).

---

## figshare deposit — `Seagrass_SEM_dataset/`
## 10.6084/m9.figshare.31289155

Large intermediate files (too big for the journal site):
- `phase4_combined_results.csv` (~378,018 rows)
- `phase5c_full_fit.csv` (505-version fit table, 12,651 rows)
- `phase6b_full_path_coefs.csv` (567,651 rows; full path coefficients — source of Fig. 7c / S24 values)
- `phase6d_universality.csv` (12,608 rows)
- per-condition `phase5c_full_fit.csv` pools for the Table S6 site-balance analysis (186 / 452 / 1830 / 75 universal models)
- `phase6e_full_validation.csv`

---

## Notes on numbering and SR labels

- **697 vs 505**: `phase7_universal_candidates.csv` holds 697 candidates that already satisfy six of the eight fit criteria plus regional universality. `phase9_recalc_strict505_final.R` adds TLI ≥ 0.95 & AGFI ≥ 0.95 to yield the 505 universal models. All main/Supplementary figures and the main text use the 505 version.
- **SR_score labels**: figures, tables, and text use **SR_score1 = microbiome** and **SR_score2 = chemistry**. Internal data columns use the opposite convention (`.SR1` / `sr1` = chemistry; `.SR2` / `sr2` = microbiome); the re-label is applied only at display/output (see `internal_lhs` column in `phase9_sr_path_summary_strict505.csv`). Values are unaffected.
- **Source Data**: the `satellite_stats/` CSVs are the Source Data for Fig. 1 and Fig. S3–S6 (BH-adjusted q-values and bin counts included).

---

## Acknowledgement

- Python code: tested with Python 3.10.
- R code: requires the libraries declared at the top of each `.R` file (e.g. `vegan`, `lavaan`, `lightgbm`, `xgboost`, `randomForest`, `arules`, `zCompositions`, `compositions`).
- Python plots use Helvetica by default and fall back to Arial if unavailable.
- Analysis scripts in this repository were developed with the assistance of Claude (Anthropic). All code was critically reviewed, tested, and validated by H. Miyamoto.
