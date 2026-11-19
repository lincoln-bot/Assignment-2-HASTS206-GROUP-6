# HASTS206 Assignment 2: Applied Demographic Analysis — Group 6

Reproducible Python analysis, Power BI dashboard, demographic projections, three-state Markov insured modeling, and district clustering for **HASTS206 Assignment 2** (University of Zimbabwe, Department of Demography, Settlement and Development).

**Data Disclaimer:** All datasets, population counts, vital rates, insured transition parameters, and findings in this repository are based entirely on **synthetic/hypothetical teaching data** generated for academic purposes.

## Repository Structure

Assignment-2-HASTS206-GROUP-6/
├── Assignment_2_Dataset.zip                 # Raw synthetic input archive (districts, age_sex, life_table_inputs, projection_scenarios, insured_transitions)
├── assignment2_demographic_analysis.ipynb   # Editable Python analysis notebook (Colab / Jupyter)
├── assignment2_demographic_analysis.html    # Executed HTML version of the Python notebook with all outputs & plots rendered
├── HASTS206_Group6_Assignment2.pbix         # Interactive 4-page Power BI Desktop dashboard
├── outputs/                                 # Generated analytical CSVs and PNG plots consumed by Power BI & the report
│   ├── before_analysis_quality_log.csv
│   ├── common_data_quality_report.csv
│   ├── q1a_demographic_indicators.csv
│   ├── q1b_demographic_rates.csv
│   ├── q1c_abridged_life_table.csv
│   ├── q2b_cohort_component_totals.csv
│   ├── q2c_projection_method_comparison.csv
│   ├── q3_expected_occupancy.csv
│   ├── q3_expected_benefit_payments.csv
│   ├── q4_district_clusters.csv
│   ├── q4_cluster_centroids.csv
│   └── *.png                                # Population pyramids, elbow plot, and silhouette plots
└── README.md                                # Project overview, dependencies, and rerun instructions


## Required Python Packages

The notebook runs on **Python 3.10+** and uses the following standard scientific libraries:

* `pandas`
* `numpy`
* `scipy`
* `scikit-learn`
* `matplotlib`
* `seaborn`

To install all dependencies locally in one command:

```bash
pip install pandas numpy scipy scikit-learn matplotlib seaborn

## How to Rerun the Analysis

### Option A: Run in Google Colab (Zero Manual File Uploads)

1. Open `assignment2_demographic_analysis.ipynb` in **Google Colab**.
2. Click **Runtime $\rightarrow$ Run all**.
3. The setup cell automatically clones this repository (if not already present in the runtime), extracts `Assignment_2_Dataset.zip` into `data/` using relative paths, runs all four analytical modules (`Q1`–`Q4`), and writes all CSV outputs and charts into `outputs/`.

### Option B: Run Locally (VS Code / Jupyter)

1. Clone this repository and navigate into the project root:
```bash
git clone [https://github.com/lincoln-bot/Assignment-2-HASTS206-GROUP-6.git](https://github.com/lincoln-bot/Assignment-2-HASTS206-GROUP-6.git)
cd Assignment-2-HASTS206-GROUP-6


2. Open `assignment2_demographic_analysis.ipynb` and execute all cells from top to bottom (**Run All**). All relative paths (`data/` and `outputs/`) resolve automatically from the repository root.

---

## Power BI Dashboard (`HASTS206_Group6_Assignment2.pbix`)

The interactive Power BI Desktop workbook consumes the CSV outputs in `outputs/` across four pages:

1. **District Profiles & Life Table:** Contrasting district comparison (`D09` vs. `D19`), `district_id` slicer, baseline vital/infrastructure KPIs, and abridged life expectancy ($e_x$) curve.
2. **2030 Population Projections:** Interactive `scenario` slicer (`Low`, `Base`, `High`), `<15` and `65+` age-structure shares, 2030 age-sex distribution, and cross-method comparison (`Arithmetic`, `Geometric`, `Cohort-component`).
3. **District Clustering Profiles:** Interactive `cluster` slicer, cluster centroids in original demographic units, and full 24-district cluster assignments.
4. **Insured Occupancy & Claims:** Continuous-time three-state Markov (`H`, `I`, `D`) expected cohort occupancy across $t = 0, 1, 2$ and expected USD 1,000 death benefit payments.
