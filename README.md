# BPA-Exposure-Analysis

This project explores publicly available brand audit data from [PlasticList.org](https://www.plasticlist.org/) and supporting references to identify products and plastic types most associated with BPA (bisphenol A) — a known endocrine disruptor found in many plastic goods.

## Key Questions
- What plastic types are most likely to contain BPA?
- Which product categories show the highest BPA incidence?
- Are there specific brands or regions disproportionately represented?

## Tools Used
- Google Sheets for initial filtering
- Python (pandas, seaborn) for analysis and visualization
- GitHub for project hosting and reproducibility

## Summary
Preliminary results suggest that polycarbonate (PC) plastics, thermal paper, and certain food packaging are disproportionately associated with BPA presence. This project aims to inform both consumers and researchers about environmental health risks.

### Data Cleaning & Preparation Steps

- Downloaded the `samples.tsv` file from PlasticList.org. [tsv file](samples.tsv)
- Uploaded to Google Sheets and saved as `BPA_data`. [Download Sheet Here](BPA_data_cleaned.csv)
- Removed irrelevant columns, focusing on BPA-related information.
- Extracted unique product `tag categories` using:
  =UNIQUE(A1:A120)
- Split compound category values (comma-delimited) with:
=INDEX(SPLIT(A2, ","), 1)
- Created a list of subcategories and used:
=UNIQUE(B2:B120)
- Built a VLOOKUP table on a sheet called Categories.
Used the following formula to assign subcategories:
=VLOOKUP(D2, Categories!D:E, 2, FALSE)

### Next Steps
Visualize which subcategories have the highest BPA % of EFSA/ EPA thresholds.

Compare across products and highlight the most frequent BPA offenders.
