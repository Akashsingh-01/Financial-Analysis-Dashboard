# Financial / Revenue Analysis Power BI Project

# 💰 Financial / Revenue Analysis Dashboard – Power BI

![Power BI](https://img.shields.io/badge/Made%20with-Power%20BI-yellow?style=for-the-badge)
![Finance](https://img.shields.io/badge/Domain-Finance-blue?style=for-the-badge)
![Data Visualization](https://img.shields.io/badge/Data-Visualization-green?style=for-the-badge)

## 📊 Overview
The **Financial Analysis Dashboard** provides a 360° view of business revenue and profit performance.  
This dashboard helps track revenue growth, cost management, and profitability trends across years, categories, and regions.

---

## 🧮 Key Measures (DAX)
```DAX
Total Revenue = SUM(Financials[Revenue])
Total Cost = SUM(Financials[Cost])
Total Profit = [Total Revenue] - [Total Cost]
Profit Margin = DIVIDE([Total Profit], [Total Revenue])
YoY Growth = 
VAR CurrentYear = MAX(Financials[Year])
VAR PrevYear = CurrentYear - 1
RETURN
DIVIDE(
    CALCULATE([Total Revenue], Financials[Year] = CurrentYear) -
    CALCULATE([Total Revenue], Financials[Year] = PrevYear),
    CALCULATE([Total Revenue], Financials[Year] = PrevYear)
)
