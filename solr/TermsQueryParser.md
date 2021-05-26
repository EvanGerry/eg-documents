## 介绍 
-  Solr 官方文档地址 [Orther Parser Documents](https://solr.apache.org/guide/7_7/other-parsers.html) 


### 官方说明
- 用于filter queries 
- 在某些情况下可能比使用标准查询解析器生成布尔查询更有效 - 默认实现排除了打分


### 推荐场景
- 支持对同一个字段超多值的terms filter，可以绕开 __maxBooleanClauses__ [Solr单次请求构建Query查询的最大语句数量，默认1024]限制

### 使用语法
#### 参数
- f ： 字段，用于过滤，仅支持单个字段
- separator：用于filter value的分割字符，默认：逗号
- method：目前支持：termsFilter, booleanQuery, automaton, or docValuesTermsFilter，设定filter 底层实现，默认：termsFilter

#### 示例
- {!terms f=categoryId method=booleanQuery separator=" "}8 6 7 5309
- {!terms f=tags}software,apache,solr,lucene => tags:(software OR apache OR solr OR lucene)
- 特殊场景：需要terms query OR 上一个条件，语法调整：\_\_query\_\_:"{!terms f=tags}software,apache,solr,lucene" OR tags: special
 

