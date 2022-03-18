# 快速入门

## 常见函数

- xlrd

```python
path = "..."
# 打开文件
workbook = xlrd.open_workbook(path)
# 获取sheet对象
sheet = workbook.sheets()[0]
# 获取行列
n_rows = sheet.nrows
n_cols = sheet.ncols
# 获取元素
sheet.cell(row, col).value
```

- xlwt

```python
path = "..."
workbook = xlwt.Workbook(encoding='utf-8')
sheet = workbook.add_sheet("sheet1")
sheet.write(i, j, "[value]")
```

