# Cyber Attack Intelligence Dashboard  
**Threat Analysis & Ransomware Risk Scoring using Machine Learning and Power BI**

## The Story – Why this project exists

Ransomware groups attack companies using known vulnerabilities (CVEs) from the CISA list.  
There are more than 1,500 such CVEs — security teams can't check every one manually.

The big question:  
**Which CVEs are most likely to be used by ransomware next?**

I built this project to answer that question.

1. Took the official CISA list  
2. Used machine learning to predict ransomware risk for each CVE (0–1 score)  
3. Created a Power BI dashboard to show everything clearly

Now anyone can quickly see:
- Which vendors are most dangerous  
- Which CVEs need urgent patching  
- How the threat changed over time

## Data Source

- **Official CISA Known Exploited Vulnerabilities Catalog**  
  Link: https://www.cisa.gov/known-exploited-vulnerabilities-catalog  
- Format: CSV  
- Records: ~1,531 vulnerabilities (March 2026)

## What the dashboard shows (3 pages)

**Page 1 – Overview**  
Quick summary: total CVEs, predicted ransomware count, average risk score  
- Trend chart (monthly changes)  
- Risk distribution (donut chart)  
- Top vendors bar chart

**Page 2 – Vendor Risk Intelligence**  
- Table of vendors with red/yellow warning colors (high risk = red)  
- Bar chart of most dangerous vendors  
- Filter by vendor name

**Page 3 – High-Risk CVEs**  
- Full list of CVEs sorted by ML risk score (highest danger first)  
- Red highlighting for very high probability  
- Filter by vendor or risk level

## Files in this repository

- `Cyber_Attack_Dashboard.pbix` → Open this in Power BI Desktop to see the dashboard  
- `cyber_attack_analysis.ipynb` → Full Python code (cleaning + ML model)  
- `powerbi_main.xlsx` → Main data + ML predictions  
- `vendor_risk_summary.xlsx` → Vendor summaries  
- `monthly_trend.xlsx` → Monthly trends  
- `/screenshots/` → Pictures of all dashboard pages

 
## Technologies used

- Python + scikit-learn (Random Forest)  
- Power BI Desktop (DAX, conditional formatting, relationships)

## Model Performance (quick numbers)

- Accuracy: ~75.6%  
- ROC-AUC: ~0.75  
- Recall on ransomware cases: ~0.43

Thank you for viewing my project!