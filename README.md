# china-city [![996.icu](https://img.shields.io/badge/link-996.icu-red.svg)](https://996.icu)
中国城市json数据

## 数据库 city.db 结构:  

里面一共有三张表: province, city, country 分别代表了 省,地级市,县级市  
### 表 province 代表了省份  
* 字段 id: 主键, 自增  
* 字段 name: 省份名称; 字符串类型; 例如: 北京市  
* 字段 code: 省份的编码; 字符串类型。 例如: 110000  

### 表 city 代表地级市  
* 字段 id: 主键, 自增  
* 字段 name: 地级市名称; 字符串类型; 例如: 朝阳区  
* 字段 code: 地级市的编码; 字符串类型; 例如: 110105  
* 字段 province_id: 所属的省份的id; 数字类型。 例如: 1  

### 表 country 代表县级市  
* 字段 id: 主键, 自增  
* 字段 province_id: 所属的省份的id; 数字类型; 例如: 3   
 >(其实可以通过县级市的地级市去找省份，但是还是放进去，方便部分人使用  
* 字段 city_id: 所属的地级市的id; 数字类型; 例如: 35  
* 字段 name: 县级市名称; 字符串类型; 例如: 山海关区  
* 字段 code: 县级市的编码; 字符串类型; 例如: 130303   

#### 索引信息:
建立了三个索引,分别是:  
* CREATE INDEX "country_c7141997" ON "country" ("city_id");  
* CREATE INDEX "country_4a5754ed" ON "country" ("province_id");  
* CREATE INDEX "city_4a5754ed" ON "city" ("province_id");  
加快了联表查询时的速度  

# [![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)
