## 介绍 
- [Orther Parser Documents](https://solr.apache.org/guide/7_7/other-parsers.html)
- 


### 官方说明
- 用于filter queries 
- 在某些情况下可能比使用标准查询解析器生成布尔查询更有效 - 默认实现排除了打分


### 推荐场景
- 支持对同一个字段超多值的terms filter，可以绕开
### 特殊场景
