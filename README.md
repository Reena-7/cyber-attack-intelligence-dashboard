# Cyber Attack Intelligence Dashboard  
**Threat Analysis & Ransomware Risk Scoring using Machine Learning and Power BI**

## Why I built this project (simple story)

Ransomware hackers use known weaknesses (called CVEs) to attack companies and schools.  
CISA (a government security agency) publishes a public list of these dangerous CVEs — but the list has more than **1,500 entries**!

Security teams have a big problem:  
- Which CVEs should they fix **first**?  
- Which ones are most likely to be used by **ransomware** groups next?  

Checking every CVE manually takes too much time and is easy to miss important ones.  
**This project solves exactly that problem.**

I took the official CISA list → used machine learning to **predict** ransomware risk for each CVE → and built a Power BI dashboard so anyone can quickly see:

- Which vendors are most dangerous right now  
- Which specific CVEs need urgent attention  
- How the threat is changing over time  

In short: **Turn raw threat data into clear, prioritized action.**

## How the project was built (step-by-step story)

1. **Got the data**  
   Downloaded the official CISA KEV catalog (CSV file with ~1,531 vulnerabilities)

2. **Cleaned & prepared**  
   In Python (Jupyter Notebook): fixed dates, created features like vendor, product, CWE type, patch delay days

3. **Trained ML model**  
   Used Random Forest to learn patterns:  
   "Which vendors/products/CWEs appear more often in ransomware attacks?"  
   Output: probability (0–1) that a CVE will be used by ransomware

4. **Built the dashboard**  
   Exported predictions to Power BI  
   Created 3 pages with filters, colors (red = high danger), and charts

5. **Result**  
   A dashboard that tells you in seconds:  
   "Patch these 10 CVEs first — they have the highest ransomware risk."
   
## Where the data comes from

- **Official source**: CISA Known Exploited Vulnerabilities Catalog  
  (the real list used by governments and companies)  
- Link: https://www.cisa.gov/known-exploited-vulnerabilities-catalog  
- Format: CSV file  
- Number of records used: ~1,531 vulnerabilities  

## What the dashboard lets you explore

The dashboard has **4 clear pages** — each page answers a different question:

**Page 1 – Executive Overview**  
Quick summary for managers:  
- Total number of vulnerabilities  
- How many are predicted to be used by ransomware  
- Average risk score  
- Risk level distribution (donut chart)  
- Top vendors by risk (bar chart)  
- Filter by vendor or risk level

**Page 2 – Vendor Risk Intelligence**  
Deep look at companies:  
- Table of every vendor with **red/yellow color warning** (red = very high risk)  
- Bar chart of the top 10 most dangerous vendors  
- Filter by any vendor name

**Page 3 – ML Predictions & High-Risk CVEs**  
The most important list:  
- All CVEs sorted from **highest risk to lowest** (based on ML probability)  
- Red highlighting for very dangerous ones  
- Shows CVE ID, vendor, product, description, etc.  
- Filter by vendor or risk level

**Page 4 – Threat Timeline**  
How the threat changed over years:  
- KPIs: recent CVEs, recent high-risk CVEs, most recent CVE date  
- Three charts:  
  - Threat severity over time (by risk level)  
  - Total vulnerabilities discovered per year  
  - Predicted ransomware CVEs per year  
- Filter by vendor, risk level, or year

 
## Files in this repository

- `Cyber_Attack_Dashboard.pbix` → the actual dashboard file (open in Power BI Desktop)  
- `cyber_attack_analysis.ipynb` → full Python code (data cleaning + ML model)  
- `powerbi_main.xlsx` → main data + ML predictions  
- `vendor_risk_summary.xlsx` → summary per vendor  
- `monthly_trend.xlsx` → monthly trend data  
- `/screenshots/` folder → pictures of all 4 dashboard pages

## Technologies used

- **Python** + scikit-learn (Random Forest model)  
- **Power BI Desktop** (DAX measures, conditional formatting, relationships)

## Model performance (quick numbers)

- Accuracy: ~75.6%  
- ROC-AUC: ~0.75  
- Recall on ransomware cases: ~0.43  
(Recall is important — we don't want to miss dangerous CVEs)

Thank you for viewing my project!  
