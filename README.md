# Project-1 : Sales Revenue Analysis based per Region

## 🧠 Goal

The goal of this project is to identify the factors that contribute to the sales revenue, specifically whether the discount or region.

By performing data analysis using Python, this project aims to provide valuable insights that can help movie companies make more informed decisions about:
- Which region needs attention about sales strategy,
- Which region and products are the highest sales in 2024 by (Jan-Feb),
- And how to allocate resources to maximize the chances of success.

---

## ⚙️ Setup

### Importing Necessary Libraries

```python
import pandas as pd
import numpy as np
import seaborn as sns

from scipy import stats

import matplotlib.pyplot as plt
import matplotlib.mlab as mlab
import matplotlib
plt.style.use('ggplot')
from matplotlib.pyplot import figure

%matplotlib inline
matplotlib.rcParams['figure.figsize'] = (12,8)

pd.options.mode.chained_assignment = None

### Importing Necessary Libraries

import pandas as pd
df = pd.DataFrame({
    'Product': [
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol',
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol',
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol',
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol',
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol',
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol',
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol',
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol',
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol',
        'Keripik Kentang', 'Mie Instan', 'Susu Kental', 'Biskuit', 'Minuman Teh Botol'
    ],
    'Price': [
        12000, 25000, 15000, 10000, 28000,
        22000, 13000, 18000, 9000, 24000,
        17000, 20000, 16000, 11000, 26000,
        14000, 23000, 19000, 12000, 27000,
        21000, 22000, 17000, 13000, 29000,
        15000, 24000, 20000, 10000, 25000,
        18000, 26000, 15000, 9000, 27000,
        22000, 13000, 18000, 11000, 24000,
        17000, 20000, 16000, 10000, 26000,
        14000, 23000, 19000, 12000, 27000
    ],
    'Date': [
        '2024-01-02', '2024-01-03', '2024-01-04', '2024-01-05', '2024-01-06',
        '2024-01-07', '2024-01-08', '2024-01-09', '2024-01-10', '2024-01-11',
        '2024-01-12', '2024-01-13', '2024-01-14', '2024-01-15', '2024-01-16',
        '2024-01-17', '2024-01-18', '2024-01-19', '2024-01-20', '2024-01-21',
        '2024-01-22', '2024-01-23', '2024-01-24', '2024-01-25', '2024-01-26',
        '2024-01-27', '2024-01-28', '2024-01-29', '2024-01-30', '2024-01-31',
        '2024-02-01', '2024-02-02', '2024-02-03', '2024-02-04', '2024-02-05',
        '2024-02-06', '2024-02-07', '2024-02-08', '2024-02-09', '2024-02-10',
        '2024-02-11', '2024-02-12', '2024-02-13', '2024-02-14', '2024-02-15',
        '2024-02-16', '2024-02-17', '2024-02-18', '2024-02-19', '2024-02-20'
    ],
    'Distributor': [
        'Distribusi B', 'Distribusi A', 'Distribusi C', 'Distribusi B', 'Distribusi A',
        'Distribusi C', 'Distribusi B', 'Distribusi A', 'Distribusi C', 'Distribusi B',
        'Distribusi A', 'Distribusi C', 'Distribusi B', 'Distribusi A', 'Distribusi C',
        'Distribusi B', 'Distribusi A', 'Distribusi C', 'Distribusi B', 'Distribusi A',
        'Distribusi C', 'Distribusi B', 'Distribusi A', 'Distribusi C', 'Distribusi B',
        'Distribusi A', 'Distribusi C', 'Distribusi B', 'Distribusi A', 'Distribusi C',
        'Distribusi B', 'Distribusi A', 'Distribusi C', 'Distribusi B', 'Distribusi A',
        'Distribusi C', 'Distribusi B', 'Distribusi A', 'Distribusi C', 'Distribusi B',
        'Distribusi A', 'Distribusi C', 'Distribusi B', 'Distribusi A', 'Distribusi C',
        'Distribusi B', 'Distribusi A', 'Distribusi C', 'Distribusi B', 'Distribusi A'
    ],
    'Region_Code': [
        'W01', 'W02', 'W03', 'W01', 'W02',
        'W03', 'W01', 'W02', 'W03', 'W01',
        'W02', 'W03', 'W01', 'W02', 'W03',
        'W01', 'W02', 'W03', 'W01', 'W02',
        'W03', 'W01', 'W02', 'W03', 'W01',
        'W02', 'W03', 'W01', 'W02', 'W03',
        'W01', 'W02', 'W03', 'W01', 'W02',
        'W03', 'W01', 'W02', 'W03', 'W01',
        'W02', 'W03', 'W01', 'W02', 'W03',
        'W01', 'W02', 'W03', 'W01', 'W02'
    ]
})

df = pd.DataFrame(df)
df.to_csv('data.csv', index=False)
df.head()


# In[10]:


# add discount
map_discount = {
    'Keripik Kentang': 0.5,
    'Mie Instan': 0.4,
    'Susu Kental': 0.8,
    'Biskuit': 0.2,
    'Minuman Teh Botol': 0.8
}
# add discount to columns discount
df['Discount'] = df['Product'].map(map_discount) * df['Price']

# final price
df['Final_Price'] = df['Price'] - df['Discount']

df.to_csv('Sales_2024.csv', index=False)
df.head()


# In[11]:


# add sold items based on distributor
map_items = {
    ('Keripik Kentang', 'Distribusi A'): 120,
    ('Keripik Kentang', 'Distribusi B'): 150,
    ('Keripik Kentang', 'Distribusi C'): 130,
    ('Mie Instan', 'Distribusi A'): 200,
    ('Mie Instan', 'Distribusi B'): 210,
    ('Mie Instan', 'Distribusi C'): 190,
    ('Susu Kental', 'Distribusi A'): 110,
    ('Susu Kental', 'Distribusi B'): 115,
    ('Susu Kental', 'Distribusi C'): 105,
    ('Biskuit', 'Distribusi A'): 140,
    ('Biskuit', 'Distribusi B'): 130,
    ('Biskuit', 'Distribusi C'): 135,
    ('Minuman Teh Botol', 'Distribusi A'): 220,
    ('Minuman Teh Botol', 'Distribusi B'): 210,
    ('Minuman Teh Botol', 'Distribusi C'): 200,
}
# add sold items to columns
df['Sold'] = df.apply(lambda row: map_items.get((row['Product'], row['Distributor']), 0), axis=1)
df.head() 


# In[12]:


# add sales columns
df['Sales'] = df['Final_Price'] * df['Sold']
df.head()

# add Region based on Region_Code
region = {
    'W01': 'Yogyakarta',
    'W02': 'Solo',
    'W03': 'Semarang'
}
# add discount to columns discount
df['Region'] = df['Region_Code'].map(region)
df.head()


# In[13]:


# sales per region
sales_per_region = df.groupby('Region')['Sales'].sum().reset_index()
sales_per_region.head()


# In[14]:


# analyse & visual
df.groupby('Region')['Sales'].describe()


# In[29]:


import matplotlib.pyplot as plt
import seaborn as sns


sns.set(style="darkgrid")

plt.figure(figsize=(6, 3))
sns.boxplot(
    data=df,
    x='Region',
    y='Sold',
    palette='husl',  
    width=0.5
)

plt.title('Sebaran Jumlah Sales per Region', fontsize=12, fontweight='bold')
plt.xlabel('Region', fontsize=12)
plt.ylabel('Sold', fontsize=12)
plt.xticks(rotation=10)
plt.grid(axis='y', linestyle='--', alpha=0.7)

plt.tight_layout()
plt.show()


# In[18]:


import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(6, 4))
sns.scatterplot(data=df, x="Sold", y="Sales", hue="Region", s=100)
plt.title("Hubungan Produk Terjual dengan Penjualan (Sales)")
plt.xlabel("Jumlah Produk Terjual")
plt.ylabel("Sales (Rp)")
plt.grid(True)
plt.tight_layout()
plt.show()


# In[31]:


import plotly.express as px

fig = px.box(
    df,
    x="Region",
    y="Sold",
    color="Region",  # Agar tiap region warnanya beda
    title="Sebaran Jumlah Produk Terjual per Region (Interaktif)",
    labels={"Sold": "Jumlah Produk Terjual", "Region": "Wilayah"},
    template="plotly_white"
)

# Tampilkan grafik
fig.show()
