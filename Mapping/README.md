# Mapping

## Table of Contents
- [介紹](#introduce)
- [動態映射](#dynamic-mapping)
- [明確映射](#explicit-mapping)
## Introduce
定義document裡資料的欄位型別，像是在RDBMS定義Table欄位的型別

## Dynamic Mapping
在ElasticSearch裡面的Mapping預設是動態的，也代表只要新增document進Index，
會依照資料的值來推斷ElasticSearch裡的型別。

### Dynamic Mapping Templates
有些欄位不想使用Dynamic Mapping出來的型別，想要針對欄位自訂型別時可以使用，模板必須在建立index的同時建立模板

### Precautions
字串類型在Dynamic Mapping之後分別會有text及keyword型別的欄位，通常會因為方便查詢加上效能問題，會選擇把搜尋的關鍵字全部放在一個字串欄位，那這時候進去的資料分別會在text及keyword的欄位各存在一份，所以會設定關鍵字欄位進去只會有text，不會有keyword

## Explicit Mapping
當想要完全自己設定mapping時，ElasticSearch有提供手動設置欄位的映射，可以在建立Index時一起設定，也可以在資料進入index後，修改動態映射的欄位型別

