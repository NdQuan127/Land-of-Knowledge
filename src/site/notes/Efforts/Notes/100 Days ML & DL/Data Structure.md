---
{"dg-publish":true,"permalink":"/Efforts/Notes/100 Days ML & DL/Data Structure/","tags":["#on/python/pandas"],"noteIcon":""}
---

>[!summary] Definition🧩
>Pandas provides two fundamental data structures: ==Series and DataFrame==
## Series
- Series is one-dimensional array *(mảng một chiều)* that can hold any data types. 
- Key features of the Series includes:
	- **Labeling**: Each element in a Series has a label or an index, which allows for easy and *access and manipulation* of data
	- **Homogeneous Data** (dữ liệu đồng nhất): unlike lists in a Python, Series typically stores data of the same data type, ensuring consistency *(nhất quán)*
	- **Vectorized Operations**: you can thực hiện các phép toán được vector hóa trên Series, giúp việc tính toán từng phần tử hiệu quả. This feature allows you thực hiện các thao tác một cách hiệu quả trên toàn bộ columns or Series mà không cần *loops*.
- ~ Creating a Series
```python
import pandas as pd
data = [1, 2, 3, 4, 5]
series = pd.Series(data, name="MySeries")

# Vectorized Operations of Series
series = series * 2
```

## DataFrame
- A DataFrame is a two-dimensional array, tabular *(dạng bảng)* data structure with labled axes *(columns and rows)*.
- It resembles an SQL table and data chính for data analysis in Pandas.
- Key features of the DataFrame includes:
	- **Columns** (cột): Each column in a DataFrame is a [[Efforts/Notes/100 Days ML & DL/Data Structure#\|Series]].
	- **Indexing**: DataFrame have both row and column indexes, cho phép lựa chọn flexible data.
	- **Data Alignment** (căn chỉnh): Like [[Efforts/Notes/100 Days ML & DL/Data Structure#\|Series]], DataFrame can align data dựa trên label, giúp việc thao tác trở nên dễ dàng và trực quan.
	- **Data Intergration** (tích hợp): You can merge, join, and concatenate *(nối)* DataFrame để combine and analyze data from nhiều source khác nhau.
- ~ Creating a DataFrame and Renaming Columns
```python
import pandas as pd  
data = {  
 "Name": ["Alice", "Bob", "Charlie", "David"],  
 "Age": [25, 30, 35, 40],  
 "City": ["New York", "San Francisco", "Los Angeles", "Chicago"]  
}
df = pd.DataFrame(data)

#Renaming the 'Name' column to 'PersonalName'
#inplace=True, will save the changes
df.rename(columns={'Name': 'PersonalName'}, inplace=True)
```

