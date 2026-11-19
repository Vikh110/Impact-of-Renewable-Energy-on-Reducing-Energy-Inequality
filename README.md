# Impact of Renewable Energy on Reducing Energy Inequality

🏆 **First Best Paper Award** (Business Analytics & Marketing category), *IDEA Symposium 2025: Student Research Conference*, Symbiosis School for Online and Digital Learning, 26 April 2025 · [certificate](Best%20Paper%20Award.pdf)

MBA (Business Analytics) research project at the Symbiosis School for Online and Digital Learning (SSODL), Symbiosis International University, under the guidance of Dr Anuradha Goswami.

📄 [Full paper](230291412459_VishwasKhandelwal_SSODLMBAJuly2023.pdf) · 📊 [Conference slides](Presentation_IDEA_2025_VishwasKhandelwal.pptx)

---

## Research question

Renewable energy is often presented as the way to close the gap in electricity access between cities and the countryside. **Does a larger renewable share in total final energy consumption (TFEC) actually narrow the urban-rural electricity-access gap?** And what roles do installed capacity and international clean-energy finance play?

## Data

Open data from the UN Sustainable Development Goals database, **Goal 7: Affordable and Clean Energy**, for the world and its regions:

| Indicator | SDG code | File |
|---|---|---|
| Proportion of population with access to electricity (total, urban, rural) | 7.1.1 | `Access_to_Electricity_Percent.csv` |
| Renewable energy share in total final energy consumption | 7.2.1 | `Renewable_Share_Total_Final_Energy_Consumption.csv` |
| International financial flows to developing countries for clean energy (USD) | 7.a.1 | `Intl_Financial_Flows_Clean_Energy_USD.csv` |
| Installed renewable generating capacity (watts per capita) | 7.b.1 | `Renewable_Capacity_Watts_Per_Capita.csv` |

The four files are cleaned and merged into `Cleaned_final_dataset.csv`.

## Method

1. **Cleaning and merging.** Redundant columns removed, names standardised, missing and duplicate values handled, and only the relevant regions plus world totals kept.
2. **Descriptive and trend analysis** of each indicator, globally and by region.
3. **Correlation analysis.** Pearson for linear and Spearman for monotonic relationships between renewable capacity, clean-energy finance and electricity access.
4. **OLS regression** of electricity access on renewable capacity per capita and clean-energy financial flows, after a variance-inflation-factor (VIF) check for multicollinearity.
5. **Disparity analysis.** The urban-rural access gap over time, per region.
6. **Efficiency comparison.** Energy output per USD invested, by technology.

## Key findings

| | Result |
|---|---|
| Renewable capacity per capita vs electricity access (world) | Pearson r = **0.97**, Spearman ρ = **0.99** |
| Clean-energy financial flows vs electricity access | Weak: r = 0.21 |
| OLS model (world) | **R² = 0.956** (adjusted 0.947), F = 107.4, p < 0.001; VIF = 1.007 for both predictors |
| Renewable capacity per capita | Coefficient 0.0325, **p < 0.001** (significant) |
| Clean-energy financial flows | Coefficient 6.5 × 10⁻⁵, p = 0.086 (not significant) |
| Global urban-rural access gap | Fell from **~22% (2010) to under 14% (2022)** |

- **Capacity matters more than money.** Installed renewable capacity is strongly linked to electricity access. Clean-energy finance on its own is not, which points to how well funds are allocated and deployed.
- **Renewables are not the whole story.** In South-Eastern and Southern Asia the access gap shrank even where the renewable share stagnated or fell. Growth, targeted rural electrification and infrastructure investment played a large part. Sub-Saharan Africa still had the widest gap, above 50% in 2022.
- **Technology mix.** Hydropower received the largest share of investment and accounts for the most capacity per capita. Wind produced the most energy per USD invested.

**Conclusion.** Renewable energy is a strong driver of wider electricity access globally. Whether it reduces the urban-rural divide depends on infrastructure, policy and fair distribution, region by region.

**Main limitation.** The urban-rural access gap is one measure of energy inequality. It does not capture affordability or quality of supply. The full list of limitations is in the paper.

## Repository contents

| File | Purpose |
|---|---|
| `Data Cleaning.ipynb` | Cleans each raw UN SDG download into one indicator file |
| `Descriptive and Trend Analysis RE Impact on EI.ipynb` | Merges the four indicator files into `Cleaned_final_dataset.csv`; descriptive statistics and regional trends |
| `Advanced analytics RE impact over EI.ipynb` | Correlation, urban-rural disparity and technology-efficiency analysis |
| `Part 2 Advanced Analytics.ipynb` | Correlations, VIF check, OLS regression and disparity analysis |
| `*.csv` | Raw indicator files and the merged dataset |
| `230291412459_VishwasKhandelwal_SSODLMBAJuly2023.pdf` | Full research paper |
| `Presentation_IDEA_2025_VishwasKhandelwal.pptx` | Slides presented at the IDEA Symposium 2025 |
| `Best Paper Award.pdf` | Award certificate |

## How to run

```bash
pip install -r requirements.txt
jupyter notebook
```

The notebooks read their data from the repository root. `Data Cleaning.ipynb` starts from the raw UN SDG downloads, which are not included. The four cleaned indicator files it produces are included, so start with `Descriptive and Trend Analysis RE Impact on EI.ipynb`.

## Author

**Vishwas Khandelwal** · [GitHub](https://github.com/Vikh110) · [LinkedIn](https://www.linkedin.com/in/vishwas-k-07842a283/)
