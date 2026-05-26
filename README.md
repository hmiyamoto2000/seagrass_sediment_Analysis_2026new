# seagrass_sediment_Analysis_2026

Analysis code for the seagrass marine-sediment study.

Raw data CSVs are deposited on the journal's related site, except for the
public Japan Meteorological Agency data
(https://www.data.jma.go.jp/kaiyou/data/db/kaikyo/series/engan/engan.html)
used for **Fig. 2 / Fig. S5**.

Materials are distributed as zipped folders; each zip contains the input
files and code (Python / R) needed to reproduce the listed figures and
tables.

---

## File map

| Zip | Figures | Tables |
|---|---|---|
| `Fig1_Ex1_S1_S2_S3_S4.zip` | Fig. 1, ED Fig. 1, Fig. S1–S4 | — |
| `Fig2a_S5.zip` | Fig. 2, Fig. S5 | — |
| `Fig3_Ex34_S15.zip` | Fig. 3, ED Fig. 3, ED Fig. 4, Fig. S15 | Table S3 |
| `Fig4a.zip` / `Fig4b.zip` | Fig. 4a, Fig. 4b | — |
| `Fig5ab.zip` | Fig. 5a, Fig. 5b | — |
| `Fig5c_Ex5_S18_S19_S20.zip` | Fig. 5c, ED Fig. 5, Fig. S18–S20 | Table S4, Table S5 |
| `FigS8_S10-2.zip` | Fig. S8, S9, S10 | Table S1, Table S2 |
| `FigS11.zip` | Fig. S11 | — |
| `FigS12_S13.zip` | Fig. S12, S13 | — |
| `FigS14.zip` | Fig. S14 | — |
| `FigS16.zip` | Fig. S16 | — |
| `FigS17.zip` | Fig. S17 | — |
| `FigS21.zip` | Fig. S21 | — |

**No code / data (figure itself is the content):** ED Fig. 2 (workflow), Fig. S6 (sediment photographs), Fig. S7 (sampling-method photographs).

---

## Figure legends

**Fig. 1** — Satellite characterisation of seagrass-bearing waters in four Japanese oceanographic regions.
**Fig. 2** — Study regions with seagrass meadows in Japan.
**Fig. 3** — Energy landscape analysis of the symbiotic candidate feature components in marine sediments.
**Fig. 4** — Distance-based RDA of symbiotic bacterial and eukaryotic communities and their relationships with chemical characteristics in marine sediments.
**Fig. 5** — Symbolic regression and collective structural equation model of seagrass-sediment holobiont components.

**ED Fig. 1** — Reduced temperature sensitivity of water quality at study sites stratified by CHLA baseline.
**ED Fig. 3** — Assessment of the **biome** feature in marine sediments.
**ED Fig. 4** — Assessment of the **chemical** feature in marine sediments.
**ED Fig. 5** — Filtering of 378,018 candidate SEM models down to 505 universal models reveals diminishing returns of model complexity.

**Fig. S1** — Annual comparison of bloom frequency, sediment variability, and SST at satellite-surveyed sites.
**Fig. S2** — Unstratified comparison of temperature sensitivity (necessity of CHLA baseline stratification).
**Fig. S3** — CDOM and PAR at study sites vs. other Japanese coastal sites.
**Fig. S4** — Satellite characterisation of Ariake Bay as a within-region test of the seagrass effect.
**Fig. S5** — Temperature of the adjacent waters surveyed in this study.
**Fig. S8** — Symbiotic bacterial diversity in the marine sediment.
**Fig. S9** — Symbiotic eukaryotic diversity in the marine sediment.
**Fig. S10** — NMDS of symbiotic bacterial and eukaryotic diversity.
**Fig. S11** — Relative abundance of bacterial and eukaryotic populations.
**Fig. S12** — Difference-in-differences for symbiotic bacterial families (D_4 level).
**Fig. S13** — Difference-in-differences for symbiotic eukaryotes (D_4 level).
**Fig. S14** — Cross-kingdom dbRDA and variation partitioning of bacterial and eukaryotic communities.
**Fig. S15** — Feature selection using four machine-learning approaches (AA, Random Forest, XGBoost, LightGBM).
**Fig. S16** — Difference-in-differences for the chemical indices.
**Fig. S17** — Feature selection based on stochastic symbolic regression.
**Fig. S18** — Composition of symbolic regression (SR) pairs across 505 universal SEM models.
**Fig. S19** — Filter stringency at the SEM enumeration step.
**Fig. S20** — Robustness of the holobiont network across fit-criteria stringency.
**Fig. S21** — Profiling of key negative eukaryotes in a collective SEM model.

---

## Tables

- **Table S1** — α-diversity statistics for the targeted regions.
- **Table S2** — NMDS (β-diversity) statistics for the targeted regions.
- **Table S3** — Pairwise precision-matrix elements: (a) biome network (ED Fig. 3b); (b) chemical network (ED Fig. 4b).
- **Table S4** — Symbolic regression formula composition for the SEM pipeline.
- **Table S5** — Variable prevalence and qualified SR pairs from the SEM screening pipeline.

---

## Notes

- Python code: tested with Python 3.10.
- R code: requires the libraries declared at the top of each `.R` file (e.g. `vegan`, `lavaan`, `lightgbm`, `xgboost`, `randomForest`, `arules`).
- Python plots use Helvetica by default and fall back to Arial if unavailable.
- Analysis scripts in this repository were developed with the assistance of Claude (Anthropic). All code was critically reviewed, tested, and validated by H.Miyamoto.
  
