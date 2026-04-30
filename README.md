# Banking on the Future: Who's Still Left Out of the Global Financial System?

A data-driven blog post analysing financial inclusion across 152 countries aiming to answer the questions: who is still locked out of the global banking system in 2025, what predicts inclusion, and how is mobile money rewriting the picture in low-income regions?

Built for BEE2041 (Data Science in Economics) at the University of Exeter, May 2026.

## The blog

The final blog post is blog.ipynb at the project root. To view it as a rendered HTML page, click here [View the blog post here]()

## Project structure

```
unbanked-world/
├── blog.html                   # Final blog post converted to .html
├── README.md                   # This file
├── LICENSE
│
├── data/
│   ├── raw/                    # Original sources, untouched
│   │   ├── GlobalFindexDatabase2025.csv
│   │   ├── demographics.csv          # Pulled from World Bank API
│   │   └── world_bank_gdp_per_capita.csv  # Pulled from World Bank API
│   ├── interim/                # Intermediate cleaning outputs
│   │   └── worldbank_gdp_clean.csv
│   │   └── findex_clean.csv
│   └── processed/              # Final analysis-ready files                        
│       └── merged_dataset.csv  # Master file: 152 countries × 17 variables
├── scripts/
│   ├── data_cleaning.ipynb     # Step 1: fetch from API, clean, merge
│   └── data_analysis.ipynb     # Step 2: build charts, run regressions
│
└── outputs/
    ├── account_ownership_map.html              # Figure 1
    ├── account_ownership_by_region.html        # Figure 2
    ├── unbanked_demographic_chart.html         # Figure 3
    ├── gdp_vs_account_ownership_scatter.html   # Figure 4
    ├── mobile_vs_traditional_by_region.html    # Figure 5
    ├── regression_table.html                   # Table 1
    └── blog_post.html                          # Rendered blog 
```

## Data sources

The dataset was built by combining two source families, both from the World Bank, joined by ISO-3 code.

**Global Findex Database 2025** is a household-level survey covering more than 150 countries, run every three years. Downloaded the country-level data as a CSV from the [World Bank's Findex page](https://www.worldbank.org/en/publication/globalfindex/download-data?utm_source=chatgpt.com). 

**World Bank Open Data API** — accessed via the `requests` library. Provides:

- Demographic breakdowns of account ownership: gender, within-country income tercile, and education.
- GDP per capita in current US dollars.

The merged dataset covers 152 countries with 17 variables.

## Setup

Requires Python 3.10 or later. From the project root:

```bash
pip install pandas numpy plotly statsmodels stargazer requests jupyter nbconvert
```

## How to replicate

Run the two notebooks in `scripts/` in the order 
1. data_cleaning.ipynb
2. data_analysis
Then open `blog.ipynb`.

## Author

Sophia Marathas, BEE2041 Empirical Project, University of Exeter, 2026.
