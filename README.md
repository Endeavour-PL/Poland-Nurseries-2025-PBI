# 👶 Nurseries and Childcare Clubs in Poland – 2025 (Power BI Report)

Power BI dashboard based on the official national register of institutions providing care for children under 3 years old (data from 2025).  
The report allows you to analyze the number of facilities and places, enrollment, and fees, broken down by region and settlement type.

---

## 🔧 Data Source

- Public dataset from: [dane.gov.pl](https://dane.gov.pl/pl/dataset/4802)
- Resource: **Rejestr żłobków i klubów dziecięcych – lista instytucji**  
- License: **CC0 1.0 (Creative Commons Zero)**

---

## 🧹 Data Processing

The dataset was pre-cleaned and transformed in Excel before being imported to Power BI.

### Excel (`R-Z_instytucje_v08.xlsx`):

- Records were removed or marked as missing if:
  - **Base monthly fee < 600 PLN** → treated as *missing data*
  - **Daily food fee < 8 PLN** → treated as *missing data*
  - **Enrolled children > available places** → number capped to available places
  - **Missing number of places** → number of children set to null
  - **Places = 0–4** → treated as *missing data*
- New columns added:
  - `Settlement type` (city / village) – inferred using TERYT keywords
  - `Town name` – cleaned version of original names
  - `Institution status` (Public / Private) – derived from provider information
  - Technical ID columns for filters: voivodeship, institution type, status, settlement type, accessibility

### Power BI (Power Query & Model):

- Harmonized voivodeship names (first letter capitalized)
- Removed irrelevant or duplicate columns:
  - ZIP code, institution name
  - Places/children funded by KPO / FERS
  - KPO/FERS food fees
- Added categorical columns for charting:
  - `Fee bracket` (e.g., “301–400 PLN”)

---

## 🌟 Dashboard Highlights

- **Star schema** with a clean fact-dimension model
- **Dynamic measures** with dropdown-based selection:
  - Average, median, standard deviation, percentiles (10%–100%)
- **Interactive slicers**:
  - Number of children / places
  - Monthly fees
  - Food fees (monthly / daily)
- **Modern and clean layout**:
  - White background, orange framing
  - Compact composition, dropdown filters, instructional tooltip
- Data versioning and full documentation of transformation logic

---

## 📁 Files in Repository

| File | Description |
|------|-------------|
| `R-Z_instytucje_v08.xlsx` | Final processed dataset |
| `RZ-Institutions-Poland-2025-v01_PL.pbix` | Power BI dashboard file in Polish |
| `LICENSE` | CC0 license |
| `README.md` | This file 😊 |

---

## 📎 License

This project is licensed under **Creative Commons Zero (CC0 1.0)** – feel free to copy, modify, and use it in any context, including commercially.

Source: [Rejestr żłobków i klubów dziecięcych – lista instytucji](https://dane.gov.pl/pl/dataset/4802)

---

📌 Created by **Filip Jasiński** – research consultant, analyst, and data visualization designer  
🔗 [LinkedIn – Filip Jasiński](https://www.linkedin.com/in/filip-j-80689681/)
