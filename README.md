# Project-1 : Sales Revenue Analysis based per Region

## 🧠 Goal

The goal of this project is to identify the factors that contribute to the sales revenue, specifically whether the discount or region.

By performing data analysis using Python, this project aims to provide valuable insights that can help FMCG companies make more informed decisions about:
- Which region needs attention about sales strategy
- Which region and product are the highest sales by period
- How to allocate sales strategy to maximize the chances of success

---

## ⚙️ Setup

### Reading update Data Frame
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/main/Data%20Frame%20Read.png?raw=true)

### Augmenting data with additional columns
1. Add discount to make final price
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/65eac7ad447ade602259f0dd6ae4ad043fd501e9/Columns%20Pertama.png?raw=true)
2. Add sold items based on distributor 
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/6401998f03e06c93f61850f5756e3b1d38dc7113/Columns%20Kedua.png?raw=true) 
3. Add region name based on code
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/6401998f03e06c93f61850f5756e3b1d38dc7113/Columns%20Ketiga.png?raw=true)
4. Sales per region
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/6401998f03e06c93f61850f5756e3b1d38dc7113/Columns%204.png?raw=true)
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/6401998f03e06c93f61850f5756e3b1d38dc7113/Columns%20keempat.png?raw=true)

## 🧑🏻‍💻 Data Explore
### What was the best sales based per region?
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/6401998f03e06c93f61850f5756e3b1d38dc7113/Columns%20kelima.png?raw=true)

## 📊 Visualize the products 
### Relation of sales to product
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/6401998f03e06c93f61850f5756e3b1d38dc7113/Visual%20pertama.png?raw=true)
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/6401998f03e06c93f61850f5756e3b1d38dc7113/Visual%201.png?raw=true)
### Distribution of sales and area
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/6401998f03e06c93f61850f5756e3b1d38dc7113/Visual%20kedua.png?raw=true)
![](https://github.com/justnnik/Project-1-Sebaran-Jumlah-Sales-per-Region/blob/6401998f03e06c93f61850f5756e3b1d38dc7113/Visual%202.png?raw=true)

## 📈 Conclusion
1. The Yogyakarta region recorded the most stable sales.
2. The Solo region had the highest average sales but was the least stable (possibly due to a large outlier).
3. The Semarang region showed average sales in terms of average and distribution.

## 🧾 Recomendation
1. With average sales varying across regions, customer segmentation can help understand shopping behavior.
2. Evaluate sales from the Solo region, such as whether these transactions are valid or should be excluded from the overall trend analysis also
   conduct a boxplot analysis to identify extreme outliers. Focus on high-transaction customers and ensure their loyalty is maintained.
3. Yogyakarta demonstrates stable sales, so promotional strategies can be focused on increasing purchase volume or frequency.
4. Promotional strategies for the Semarang region can target increasing the average transaction value (upselling).

