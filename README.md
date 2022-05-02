# dogukan_deneme
Python Codes

import pandas as pd
from matplotlib import pyplot as plt
import numpy as np
from matplotlib import colors
from matplotlib.ticker import PercentFormatter
df = pd.read_excel(r'C:\Users\Dparil\Desktop\Book1.xlsx')
print(df.describe())
print(df.head())

df.rename(columns={'Traffic': 'T', 'Customers': 'C'}, inplace=True)

# Creating histogram
df.hist()
plt.show()

print(df.head())

# New Data imported
df_v2 = pd.read_excel(r'C:\Users\Dparil\Desktop\Monthly PV - Customer Data_.xlsx', sheet_name= 'Sheet2')
print(df_v2)
print(df_v2.head())

# Filtering columns
a = df_v2.groupby('BuyCategory')
a.head()
print(df_v2)
df_v3 = pd.DataFrame(df)
print(df_v3)
filt = df['Category'] == 'Altın Mağazası'
print(df[~filt])

# Dividing columns by 1000 and drawing histogram
print(df_v2)
df_v2['Product View'] = df_v2['Product View'].div(1000).round(2)
print(df_v2)

# Creating histogram
df_v2.hist()
plt.show()

# 32 Adet Row ile Yapılan Çalışma
df.rename(columns={'Product View': 'PV', 'Customer': 'C'}, inplace=True)
print(df)
df['C'] = df['C'].div(1000000).round(2)
print(df)
df['PV'] = df['PV'].div(1000000).round(2)
print(df)

df.hist()
plt.show()
