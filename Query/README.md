# Query

## Table of Contents
- [General Info](#general-Info)
- [資料回傳大小、欄位](#data-size-field)
- [複合查詢](#compound-queries)
- [全文查詢](#full-text-queries)
- [欄位等級查詢](#term-level queries)

## General Info
在ElasticSearch屬於Query Context
特性:
- 計算查詢匹配的分數，分數越高排序越前面
- 快取 query 裡的子查詢結果且包含匹配分數

#請盡量不要使用 Script、Wildcard，因為會有效能問題

## Data Size Field
設定資料回傳的欄位及大小
```json
GET /kibana_sample_data_ecommerce/_search
{
  "size": 20,
  "from": 0,
  "query": {
  },
  "_source": {
    "excludes": ["order_id","order_date"],
    "includes": ["*"]
  }
}
```

## Compound Queries
### BooleanQuery
查詢符合條件的資料，如RDBMS 查詢多個條件

- must
	必須出現在查詢結果的條件，類似RDBMS的=與&&
- filter
	在ElasticSearch屬於Filter Context
	特性:
	- 不計算匹配分數
	- 處理速度較快
	- 不會快取其他有相關性計分的 query
	#優先建議使用filter
- should
	有可能出現在查詢結果中，類似RDBMS的||
- must_not
	與must反意，不得出現在查詢結果

## Full text queries
### match_all
查詢所有資料，請盡量配合size與from使用

### match
標準查詢

- query
	查詢的值
- operator
	查詢條件OR或AND
- fuzziness
	模糊查詢，預設auto
	[請參閱](https://www.elastic.co/guide/en/elasticsearch/reference/current/common-options.html#fuzziness)

### multi_match
單個值查詢多個欄位

- query
	查詢的值
- operator
	查詢條件OR或AND
- fields
	 欄位
	
## Term-level queries
### Term
單個欄位查詢

### Terms
單個欄位查詢多個值

### Range
範圍查詢