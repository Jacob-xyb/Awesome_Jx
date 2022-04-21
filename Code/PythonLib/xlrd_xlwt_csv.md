# 快速入门

## 常见函数

- xlrd

新版xlrd不能读取xlsx文件，至少目前是的。

推荐使用 `xlrd==1.2.0` 版本。

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

- csv

```python
path = "..."
f = open(path, "w")
# 如果不加 lineterminator='\n'; 就会每次在末尾追加空行
w = csv.writer(f, lineterminator='\n')
# 两种实现方式
# ==写入一行
w.writerow(text)	# 切记要写在list里面
# ==写入多行
w.writerows(texts)
```

