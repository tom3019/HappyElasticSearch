# 快快樂樂學ElasticSearch系列

## Table of Contents

- Mapping

- Setting

- Shard & Node

- [Metadata](./MetaData/README.md)

- [Query](./Query/README.md)

- Command

- Aggregation

- ElasticSearch in dotNet

  

## General Info

ElasticSearch 非常基礎教學，希望能幫助到剛使用ElasticSearch的朋友，

此教學並不包含所有完整的訊息，僅從專案上使用的經驗來撰寫




## Technologies

- ElasticSearch 7.9.3

- Kibana 7.9.3

- ASP.NET Core

  

## Setup

```powershell
// go to this folder
$ docker-compose up
```



## ElasticSearch 與 RDBMS

| RDBMS  | ElasticSearch |
| :----: | :-----------: |
| Table  |     Index     |
|  Row   |   Document    |
| Column |     Field     |
| Schema |    Mapping    |
|  SQL   |      DSL      |





## ElasticSearch Type

### DataType

[https://www.elastic.co/guide/en/elasticsearch/reference/current/sql-data-types.html](https://www.elastic.co/guide/en/elasticsearch/reference/current/sql-data-types.html)

### FieldType

[https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-types.html](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-types.html)