#　MetaData
ElasticSearch Request Data 

## 欄位說明

### 外部的hits

- total.value
	符合查詢的資料總數
- total.relation
	eq表示完全符合
	
### max_score
內容中最大的匹配分數

### 內部的hits
- _index
	表示所在的index
- _type
	表示資料類型
- _id
	Document Id
	_ score
	匹配分數
- _source
	查詢結果的資料