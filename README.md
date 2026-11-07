<div align="center">

# -- ! HDFC Banking Performance Dashboard ! --
### *Interactive Power BI Dashboard for Deposits, Loans & Branch Analytics*

[![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Measures%20%26%20KPIs-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://learn.microsoft.com/en-us/dax/)
[![Data Model](https://img.shields.io/badge/Data%20Model-8%20Tables-4CAF50?style=for-the-badge&logo=databricks&logoColor=white)](https://powerbi.microsoft.com/)
[![Banking](https://img.shields.io/badge/Domain-Banking%20Analytics-004C8F?style=for-the-badge&logo=bankofamerica&logoColor=white)](https://powerbi.microsoft.com/)

<br/>

> *"Numbers don't just balance a bank — they tell it where to grow."*

</div>

---

## 📋 Table of Contents

- [📌 Overview](#-overview)
- [🎯 Problem Statement](#-problem-statement)
- [✨ Key Features](#-key-features)
- [🏗️ Project Structure](#️-project-structure)
- [🔄 Project Workflow](#-project-workflow)
- [💰 Part A — Deposits vs Targets](#-part-a--deposits-vs-targets)
- [🏦 Part B — Loan Portfolio](#-part-b--loan-portfolio)
- [🏢 Part C — Branch Performance](#-part-c--branch-performance)
- [🛠️ Tech Stack](#️-tech-stack)
- [📈 Results & Insights](#-results--insights)
- [🏆 Advantages](#-advantages)
- [📄 License](#-license)
- [👤 Author](#-author)
- [🙏 Acknowledgements](#-acknowledgements)

---

## 📌 Overview

The **HDFC Banking Performance Dashboard** is an interactive, three-page **Power BI** report that tracks how a bank's branch network is performing. It compares deposits against targets, monitors the loan book and EMI collections, and ranks branches by deposits, loans and transactions. The report is designed at **2560 × 1440** with KPI cards, slicers, maps, drill-down tables and a page navigator.

This project is designed to:
- Track **deposits** against **targets** and year-on-year growth
- Monitor the **loan book**, **active loans** and **EMI collection**
- Compare **branches**, **cities**, **zones** and **regions**
- Analyze **transaction** volume and types
- Practice **data modeling**, **DAX measures** and **dashboard design** in Power BI

---

## 🎯 Problem Statement

> **Objective:** Build an interactive dashboard that helps bank management monitor deposits, loans and branch performance in one place.

Bank data usually lives in separate systems for deposits, loan repayments and transactions. This dashboard brings it into one data model, so every metric can be filtered by region, zone, city, branch, product and financial period.

| 📂 Table | 📄 Type | 🔍 Description |
|----------|---------|----------------|
| DimBranch | Dimension | Branch name, city, zone, region and city tier |
| DimProduct | Dimension | Banking products such as savings accounts and loan types |
| DimAccount | Dimension | Account details |
| DimDate | Dimension | Date table with financial year, FY quarter and month |
| FactTransactions | Fact | Transactions with transaction type |
| FactLoanRepayments | Fact | Loan repayment and EMI records |
| BranchDepositTargets | Fact | Deposit targets for each branch |
| MeasureTable | Measures | Holds all DAX measures and KPIs |

The goal is to demonstrate **end-to-end BI skills** — from a star-schema model to measures to a polished, navigable report.

---

## ✨ Key Features

| Feature | Description |
|--------|-------------|
| 📑 **3 Report Pages** | Deposits vs Targets, Loan Portfolio and Branch Performance |
| 🎛️ **Rich Slicers** | Filter by Region, Zone, Branch, Product, Financial Year, Quarter and City Tier |
| 🔢 **KPI Cards** | Total Deposits, Target, Achievement %, YoY Growth %, Loan Book, Active Loans, EMI Collection, Transactions |
| 🎯 **Target Tracking** | Actual deposits compared with target by month |
| 🗺️ **Maps** | Deposits, loan exposure and branch network performance by city |
| 🔽 **Drill-down Tables** | Region > Zone > City > Branch hierarchy |
| 📈 **Trend Charts** | Deposit, EMI collection and transaction trends with drill-down by year, quarter and month |
| 🍩 **Distribution Charts** | Deposits by product, loans by region, transactions by type |
| 🏅 **Best Branch** | Top performing branch highlighted in a KPI card |
| 💡 **Key Insights Panels** | Written takeaways on every page |

---

## 🏗️ Project Structure

```
📦 hdfc-banking-dashboard/
│
├── 📄 HDFC_Dashboard.pbix   ← Power BI report (data model + 3 pages)
│
└── 📄 README.md             ← Project documentation
```

---

## 🔄 Project Workflow

```
Raw Banking Data (Deposits · Loans · Transactions · Targets)
      │
      ▼
┌─────────────────────────────┐
│   Load & Clean Data         │  ← Dimension and fact tables
└────────────┬────────────────┘
             │
             ▼
┌─────────────────────────────┐
│   Build Data Model          │  ← Dim + Fact tables + MeasureTable (DAX)
└────────────┬────────────────┘
             │
   ┌─────────┼─────────────┐
   ▼         ▼             ▼
┌────────┐┌──────────┐┌───────────┐
│Deposits││  Loan    ││  Branch   │
│vs Targ.││Portfolio ││Performance│
└───┬────┘└────┬─────┘└─────┬─────┘
    └──────────┴────────────┘
               │
               ▼
┌─────────────────────────────┐
│  Slicers: Region · Zone     │
│  Branch · Product · FY      │
└────────────┬────────────────┘
             │
             ▼
   KPI Cards + Charts Update
             │
             ▼
   Insights for Bank Management ✅
```

---

## 💰 Part A — Deposits vs Targets


<img src="assets/Deposits vs Targets page 1.png">

### 📝 1. What does this page show?

The **Deposits vs Targets** page answers: *how much have we collected, how does it compare with target, and where does it come from?*

---

### 🗺️ 2. Visuals — Overview

| Visual | Type | Fields Used |
|--------|------|-------------|
| 🔢 Deposit KPIs | KPI Cards | `Total Deposits Cr`, `Deposit Target Cr`, `Achievement %`, `YoY Growth %` |
| 📈 Deposit Trend | Line Chart | `FY`, `FY Quarter`, `Month Label`, `Total Deposits Cr` |
| 📊 Actual Deposits vs Target (Monthly) | Clustered Column | `Month Label`, `Total Deposits Cr`, `Deposit Target Cr` |
| 🍩 Deposits by Product Type | Donut | `ProductName`, `Total Deposits Cr` |
| 🗺️ Geographic Deposit Distribution | Map | `City`, `Total Deposits Cr` |
| 🧾 Region Summary | Matrix | Region > Zone > City > Branch with deposits, target, variance, achievement % and YoY growth |

**Slicers:** Region, Zone, Branch, Product, Financial Year, FY Quarter, Month

---

## 🏦 Part B — Loan Portfolio

<img src="assets/Loan Portfolio page 2.png">

### 🔍 3. What does this page show?

The **Loan Portfolio** page answers: *how big is the loan book, where is the exposure, and how are EMIs being collected?*

| Visual | Type | Fields Used |
|--------|------|-------------|
| 🔢 Loan KPIs | KPI Cards | `Loan Book Cr`, `Active Loans`, `EMI Collection Cr`, `Avg Loan Size Lakh` |
| 📈 EMI Collection Trend | Line Chart | `FY`, `FY Quarter`, `Month`, `EMI Collection Cr` |
| 🍩 Loan Status Distribution | Donut | `Region`, `Loan Book Cr` |
| 📊 Outstanding Loans by Product | Clustered Bar | `ProductName`, `Active Loans` |
| 🟦 Loan Portfolio by Product | Treemap | `ProductName`, `Loan Book Cr` |
| 🗺️ Loan Exposure by Geography | Map | `City`, `Loan Book Cr` |
| 🧾 Region Summary | Matrix | Region > Zone > Branch with loan book, EMI collection, active loans and average loan size |

**Slicers:** Region, Zone, Branch, Product, Financial Year, Quarter

---

## 🏢 Part C — Branch Performance


<img src="assets/Branch Performance page 3.png">

### 🔍 4. What does this page show?

The **Branch Performance** page answers: *which branches, cities and branch types perform best across deposits, loans and transactions?*

| Visual | Type | Fields Used |
|--------|------|-------------|
| 🔢 Branch KPIs | KPI Cards | `Total Branches`, `Total Transactions`, `Avg Transaction Value`, `Best Branch`, `Best Branch Info` |
| 📈 Transactions Trend | Line Chart | Year > Quarter > Month > Day, `EMI Collection Cr` |
| 📊 Revenue by Branch Hierarchy | Clustered Bar | Region > Zone > City > Branch, `Total Deposits Cr` |
| 📊 Branch Type Performance | Clustered Column | `City`, `Total Transactions`, `Loan Book Cr` |
| 🍩 Transactions by Type | Donut | `TransactionType`, `Total Transactions` |
| 🗺️ Branch Network Performance | Map | `City`, `Total Deposits Cr` |
| 🧾 Branch Summary | Matrix | Deposits, loan book, transactions, achievement % and active loans by branch |

**Slicers:** Region, Zone, Branch, City Tier, Financial Year, Quarter

---

## 🛠️ Tech Stack

| Tool | Version | Purpose |
|------|---------|---------|
| 📊 **Power BI Desktop** | Latest | Report authoring and data modeling |
| 🧮 **DAX** | Built-in | Measures such as Total Deposits Cr, Achievement %, YoY Growth %, Loan Book Cr, EMI Collection Cr |
| 🗃️ **Data Model** | 8 tables | 4 dimensions, 3 fact tables and 1 measure table |
| 🗺️ **Map Visuals** | Built-in | City-level distribution of deposits and loans |
| 🧭 **Page Navigator & Buttons** | Built-in | Moving between pages |
| 🖼️ **Custom Canvas Images** | PNG | Page backgrounds and layout |

---

## 📈 Results & Insights

The dashboard's own insight panels report the following:

- 💰 **Deposits:** Total deposits are ₹237.1 Cr, down 1.5% from the previous year
- 🎯 **Targets:** Target of ₹16,466.7 Cr, giving an achievement of 1.44%
- 🏦 **Savings Accounts** contribute the highest share (25.3%) of deposits
- 🧭 **Regions:** North and South lead deposit mobilization (₹54.1 Cr and ₹50.9 Cr)
- 📘 **Loan Book:** ₹9,760.4 Cr, down 1.73% from the previous year; Business Loan has the highest share (20.4%)
- 📍 **Exposure:** North Region has the highest loan exposure (₹2,277.0 Cr)
- 💳 **EMI:** ₹126.6 Cr collected across 39,091 active loans
- 🏅 **Top Branch:** HDFC Branch 39 (Bengaluru, North Zone) with 3.19% target achievement
- 🏙️ **Metro branches** lead in both deposits (₹148.1 Cr) and loan book (₹6,089.2 Cr)
- 🔁 **Transactions:** EMI leads with 14.5%; all 7 transaction types contribute roughly equally

---

## 🏆 Advantages

| Advantage | Detail |
|-----------|--------|
| 🎓 **Complete Bank View** | Deposits, loans and branch performance in one report |
| 🎛️ **Flexible Filtering** | Slicers for region, zone, branch, product, year and quarter |
| 🔄 **Reusable Model** | Star schema with a dedicated MeasureTable for all DAX measures |
| 🔽 **Drill Down** | Region > Zone > City > Branch and Year > Quarter > Month |
| 🎯 **Target Tracking** | Actual vs target shown by month with achievement % |
| 🗺️ **Location Insight** | Maps on every page show where deposits and loans are concentrated |
| 💡 **Built-in Insights** | Key takeaways written directly on each page |
| 🖥️ **Clean Layout** | Consistent 2560 × 1440 design with a page navigator |



## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for full details.

```
MIT License — Free to use, modify, and distribute with attribution.
```

---

## 👤 Author

<div align="center">

### Divyesh Jadav

[![GitHub](https://img.shields.io/badge/GitHub-yourhandle-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yourhandle)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/your-profile/)

> *"Every dashboard starts with a question — and ends with a better decision."*

**🎓 Role:** Data Analyst | Power BI Enthusiast \
**📍 Location:** India\
**🛠️ Skills:** Power BI · DAX · Data Modeling · Dashboard Design · Data Visualization

</div>

---

## 🙏 Acknowledgements

Special thanks to the following resources and communities that made this project possible:

- 📚 [Power BI Documentation](https://learn.microsoft.com/en-us/power-bi/) — Official Power BI reference
- 🧮 [DAX Guide](https://dax.guide/) — Complete DAX function reference
- 🎨 [Power BI Report Design Guidance](https://learn.microsoft.com/en-us/power-bi/guidance/) — Layout and design best practices
- 🖥️ [Microsoft Learn — Power BI](https://learn.microsoft.com/en-us/training/powerplatform/power-bi) — Beginner to advanced courses
- 💬 [Power BI Community](https://community.fabric.microsoft.com/) — Problem-solving support
- 📖 [Kaggle Learn](https://www.kaggle.com/learn) — Data and analytics courses

---

<div align="center">

---

*Made with ❤️ and ☕ — Last updated: 7 November, 2026*

</div>
