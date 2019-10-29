# Pandas 速查表
- Author: [HuiFer](https://github.com/huifer)
- Description: 本文为pandas方法表

**注意: pd => pandas , df => dataFrame , s => pd.Series**
#数据读取read
- 读取csv
    - pd.read_csv(file_name)
- 读取tsv
    - pd.read_table(file_name)
- 读取excel
    - pd.read_excel(file_name)
- 读取sql表
    - pd.read_sql(query,obj)
- 读取json字符串
    - pd.read_json(json_str)
- 读取html
    - pd.read_html(url)
- 读取dict类型
    - pd.DataFrame(dict)
#数据导出to
- 导出csv
    - df.to_csv(file_name)
- 导出excel
    - df.to_excel(file_name)
- 导出sql
    - df.to_sql()
- 导出json
    - df.to_json()

# 数据查看
- df.head(n) 查看数据的前n行
- df.tail(n) 查看数据的倒数n行
- df.shap 查看的 行数和列数
- df.info() 查看 dataFrame 的索引、数据类型
- df.describe() 对于数据类型为数值型的列，查询其描述性统计的内容
- df.apply(pd.Series.value_counts)  查询 dataFrame 中每列的独特数据值出现次数统计
- s.value_counts(dropna=False)  查询每个数据值出现次数统计


# 数据选取
- df[col] 返回 Series 类型的数据列
- df[[col1,cole2]] 返回 dataFrame 类型的数据列
- s.iloc[n] 按 n 选择列
- s.iloc[index] 按索引选择
- df.iloc[0,:] 选择第一行
- df.iloc[x,y] 选择第 x 行第 y 个

# 数据清洗
- df.columns =['new_col_name1','new_cole_name2'] 重命名列名称
- pd.isnull() 检查数据中空值出现的情况，并返回一个由布尔值(True,False)组成的列
- pd.notnull() 检查数据中非空值出现的情况，并返回一个由布尔值(True,False)组成的列
- df.dropna() 移除 DataFrame 中包含空值的行
- df.dropna(axis=1) 移除 DataFrame 中包含空值的列
- df.fillna(x) 将 DataFrame 中的所有空值替换为 x
- s.fillna(s.mean())  将所有空值替换为平均值,s.mean()可替换
- s.replace(x,y)  将 Series 中的所有 x 替换为' y


# 过滤,排序,分组
- df[df[col] > x ] 选择 dataFrame 指定列col中大于x的值,注df[col] > x 可填写多个条件用括号包裹df[(df[col] > 1 ) & (df[col] < 2)]
- df.sort_values(col1) 按照 dataFrame 的列col1升序(ascending)的方式对 dataFrame 做排序,ascending=False 降序
    - df.sort_values([col1,col2],ascending=[True,False]) 按照 dataFrame 的列col1升序，col2降序的方式对 dataFrame 做排序

- df.groupby(col) 按照 col 对 dataFrame 做分组
    - df.groupby([col1,col2])

# 统计
- df.describe() 得到 dataFrame 每一列的描述性统计
- df.mean() 得到 dataFrame 中每一列的平均值
- df.corr() 得到 dataFrame 中每一列与其他列的相关系数
- df.count() 得到 dataFrame 中每一列的非空值个数
- df.max() 得到 dataFrame 中每一列的最大值
- df.min() 得到 dataFrame 中每一列的最小值
- df.median() 得到 dataFrame 中每一列的中位数
- df.std() 得到 dataFrame 中每一列的标准差
