## 1. One-Hot Encoding (most common for categorical data):
```
df = pd.get_dummies(df, columns=['ColumnName'], prefix='ColumnName')
```
```
→ Creates new columns: ColumnName_A, ColumnName_B, ColumnName_C etc. with 0/1 values.

## 2. Label Encoding (if you’re using tree-based models like Random Forest or XGBoost, which don’t assume order):
```
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['ColumnName'] = le.fit_transform(df['ColumnName'])
```
→ Assigns integers automatically, but tree models handle them correctly.