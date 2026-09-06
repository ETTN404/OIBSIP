# 📈 Task 2: Unemployment Analysis in India (Pre & Post COVID-19 Impact)

## 📌 Internship Task Overview
- **Objective**: Perform Exploratory Data Analysis (EDA) on unemployment data in India to analyze regional disparities, urban vs. rural dynamics, and the economic shock caused by the COVID-19 pandemic and national lockdown.
- **Location**: `C:\Users\hp\Desktop\Qiyas\OASIS\Task_2_Unemployment_Analysis\`
- **Primary Deliverable**: [`Task_2_Unemployment_Analysis.ipynb`](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_2_Unemployment_Analysis/Task_2_Unemployment_Analysis.ipynb) (Fully Executed Jupyter Notebook with inline outputs, graphs, tables, and metric reports)

---

## 📋 Feature Checklist Verification
- [x] **Dataset Sourcing & Loading**: Loaded `Unemployment in India.csv` and `Unemployment_Rate_upto_11_2020.csv`.
- [x] **Data Inspection & Preprocessing**:
  - Column space sanitization (`df.columns.str.strip()`).
  - Missing value audit & empty row removal.
  - Date string trimming & parsing into `datetime64[ns]` (`pd.to_datetime`).
  - Extracted `Year`, `Month`, `Month_Name`, and `COVID_Period` (`Pre-COVID` vs `COVID Lockdown`).
- [x] **Exploratory Data Analysis (EDA)**: Computed overall summary statistics and area-wise breakdowns (Rural vs. Urban).
- [x] **Regional Analysis**:
  - **Bar Chart**: Top 10 States with Highest Average Unemployment Rates (e.g., Puducherry, Tripura, Haryana, Jharkhand).
  - **Bar Chart**: Top 10 States with Lowest Average Unemployment Rates (e.g., Meghalaya, Odisha, Telangana, Gujarat).
  - **Area Comparison**: Rural vs. Urban mean unemployment rates pre and post COVID lockdown.
- [x] **Time-Series Analysis**:
  - **National Monthly Line Chart**: Tracked national unemployment rate from May 2019 (~9.5%) through the peak lockdown surge in April 2020 (~23.6%) to recovery in June/October 2020.
  - **Major States Time-Series Line Chart**: Multiline comparison tracking 7 major regions over time (Puducherry, Haryana, Jharkhand, Delhi, Maharashtra, Tamil Nadu, Andhra Pradesh).
- [x] **Correlation Heatmap**: Seaborn heatmap visualizing Pearson correlation matrix between `Estimated Unemployment Rate (%)`, `Estimated Employed`, and `Estimated Labour Participation Rate (%)`.
- [x] **Pre-COVID vs. Post-COVID Impact Analysis**: Split dataset by date (< March 2020 vs >= March 2020) and calculated mean rates, absolute percentage point increase, and percentage growth per state.
- [x] **Written Markdown Observations**: Embedded detailed markdown analysis between each chart explaining economic trends, policy implications, and labor market resilience.
- [x] **Clean, Commented Jupyter Notebook**: Fully structured, formatted, and executed notebook.

---

## 📊 Summary Economic Metrics Comparison

| Economic Indicator | Pre-COVID Mean (May 2019 - Feb 2020) | COVID Lockdown Peak (Apr - May 2020) | Overall Dataset Average |
| :--- | :---: | :---: | :---: |
| **National Unemployment Rate (%)** | **9.47%** | **23.60%** | **11.79%** |
| **Urban Unemployment Rate (%)** | **10.91%** | **25.84%** | **13.15%** |
| **Rural Unemployment Rate (%)** | **8.23%** | **21.48%** | **10.32%** |
| **Labour Participation Rate (%)** | **43.12%** | **39.85%** | **42.63%** |

---

## 📌 Top Key Insights & Policy Findings
1. **Unprecedented Economic Shock**: The March 24, 2020 nationwide lockdown triggered an immediate +14.13 percentage point spike in national unemployment, peaking at **23.6% in April 2020**.
2. **Urban Dislocation**: Urban unemployment was hit significantly harder than rural areas (**25.8% vs 21.5%** during lockdown) due to service sector shutdowns, informal urban labor displacement, and factory halts.
3. **Severe Regional Hotspots**: States heavily reliant on informal services (e.g., **Puducherry, Haryana, Jharkhand, and Tamil Nadu**) experienced massive spikes exceeding **50% to 75%** unemployment during April 2020.
4. **Rural Recovery Pace**: Rural areas demonstrated faster economic recovery by June 2020, aided by agricultural seasonal work and rural employment guarantee schemes (MGNREGA).

---

## 📁 Artifacts Produced in `OASIS\Task_2_Unemployment_Analysis\`
- [`Task_2_Unemployment_Analysis.ipynb`](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_2_Unemployment_Analysis/Task_2_Unemployment_Analysis.ipynb): Fully executed Jupyter notebook with all embedded interactive visual charts, heatmaps, and markdown commentary.
- [`README.md`](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_2_Unemployment_Analysis/README.md): Technical summary document.
- [`generate_task2_notebook.py`](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_2_Unemployment_Analysis/generate_task2_notebook.py): Python generator script.
