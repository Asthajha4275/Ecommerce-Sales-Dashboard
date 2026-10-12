# E-commerce Sales Dashboard (Tableau)

An interactive Tableau dashboard for an e-commerce / retail business (DataCo) that tracks **Sales, Profit and Order Quantity**, compares them with the previous year (YTD vs PYTD), and breaks performance down by product category and market.

**Tools:** Tableau Public / Desktop (calculated fields, LOD expressions, KPI cards, dashboard design) · CSV data source

---

## 1. Business Problem

Management needs a single view of how the business is performing and how it compares with last year. Key questions:

1. What are total sales, profit and order quantity, and how have they changed year over year?
2. Which product categories are growing or declining versus the previous year?
3. Which markets hold the largest share of sales?
4. How many new customers does each market acquire every month?

---

## 2. Dataset

| Item | Detail |
|---|---|
| File | `Dataco (Abhijit database)_Dataco.csv` |
| Size | 115,746 order lines × 20 columns |
| Period | January 2016 – December 2017 |
| Orders / customers | 42,725 unique orders · 18,006 unique customers |
| Duplicates | None found |

**Key columns:** Order Id, Order Date, Customer Id, Customer Segment (Consumer / Corporate / Home Office), Customer City / State / Country, Market, Order Region, Category Name (50 categories), Product Price, Order Quantity, Sales, Order Item Total, Profit Per Order, Profit Margin.

**Data notes:** Order Date is stored as day-month-year text (e.g. 17-06-2017) and must be converted to a date field. The first column ("Additional Order items") has some blanks and the zipcode field has a few; neither is used in the dashboard.

---

## 3. Project Steps

### Step 1 – Connect the data
Connected Tableau to the CSV and checked data types. Converted **Order Date** to a proper date so that year-based comparisons work.

### Step 2 – Create calculated fields
Built the measures that power the year-over-year comparison:

| Group | Fields |
|---|---|
| Current year to date | YTD Sales, YTD Sales LOD, YTD Profit LOD, YTD Quantity LOD |
| Previous year to date | PYTD Sales, PYTD Sales LOD, PYTD Profit LOD, PYTD Quantity LOD |
| Growth % | YOY Sales %, YOY Profit %, YOY Quantity % |
| Margins and differences | Sales Margin, YOY Sales / Profit / Quantity margin, % Difference |
| Colour helpers | Positive % diff, Negative % diff (green/red formatting) |

LOD expressions let each measure be calculated for the selected year independently of the chart layout.

### Step 3 – Build the worksheets
| # | Worksheet | Purpose |
|---|---|---|
| 1 | Sales KPI | Total sales with YoY change |
| 2 | Profit KPI | Total profit with YoY change |
| 3 | Order Quantity KPI | Total quantity with YoY change |
| 4 | Category wise YTD vs PYTD Sales | Category growth versus the previous year |
| 5 | Market Share by Sales | Each market's share of total sales |
| 6 | Market wise Customer Acquisition per Month | New customers by market, month by month |

### Step 4 – Design the dashboard
Combined the worksheets into **Dashboard 1**: KPI cards across the top, then the category comparison, market share and customer acquisition charts, with consistent colours and red/green indicators for growth and decline.

### Step 5 – Interpret and share
Drew the insights below and saved the workbook as a `.twbx` so it opens with the data included.

---

## 4. Key Insights

*(Figures below are for full-year 2016 vs 2017 from the dataset; the dashboard's YTD view depends on the date selected.)*

- **Overall:** about 27.5M in total sales, 2.61M in profit and 295K units across the two years.
- **Sales grew about 5%** from 2016 (13.43M) to 2017 (14.11M).
- **Order quantity grew about 15%** (137K to 158K units), faster than sales, which suggests lower average value per unit sold.
- **Profit was flat to slightly down (about -0.5%)** (1.31M to 1.30M), so growth did not translate into higher profit.
- **Markets:** Europe (~25%), LATAM (~24%) and Pacific Asia (~22%) lead sales, followed by USCA (~20%); Africa is the smallest (~9%).
- **Top categories by sales:** Cardio Equipment, Fishing, Camping & Hiking, Cleats and Water Sports.
- **Customers:** Consumer is the largest segment (about 52% of order lines), followed by Corporate (30%) and Home Office (18%).

---

## 5. Recommendations

1. **Protect margins:** quantity is growing faster than profit, so review discounts and low-margin products.
2. **Double down on top categories** (Cardio Equipment, Fishing, Camping & Hiking) and review the declining ones in the YTD vs PYTD chart.
3. **Grow Africa**, the smallest market, with targeted acquisition campaigns.
4. **Use the monthly acquisition chart** to time marketing in markets where customer additions slow down.

---

## 6. How to Open

1. Download `Ecommerce sales Dashboard Project.twbx` and open it in Tableau Public or Tableau Desktop.
2. Open **Dashboard 1** to explore, or any worksheet tab to see a single chart.

## 7. Repository Structure

```
├── Ecommerce sales Dashboard Project.twbx   # Tableau workbook + dashboard
├── Dataco (Abhijit database)_Dataco.csv     # Source data
└── README.md
```

## 8. Skills Demonstrated

Tableau KPI cards · LOD expressions · YTD vs PYTD analysis · Calculated fields · Dashboard design · Business insight generation

---
## Architecture Diagram
![E-commerce Architecture](diagram%20(4).png)


**Author:** Astha Kumari Jha
**GitHub:** [github.com/Asthajha4275](https://github.com/Asthajha4275)
