# TDengine-Practise
take Logistics ( Location Tracking) as an example
## 建库（新数据保存一年）
```
create database logistics keep 365;
```
## 使用库
```
use logistics;
```
## 建超级表
```
create table logistics_info(ts timestamp, latitude float, longitude float, direction float, speed float) tags (id binary(16), type binary(20), goods binary(40))
```
## 建子表
```
create table c1 using smart_meters tags(‘1’,’VOLKSWAGEN’,’furniture’);
```
## 插入数据
```
insert into c1 (ts, latitude, longitude, direction, speed) values (now, 121.231, 32.132, 35.52, 89.33)
```
## 查询数据
```
select ts, latitude, longitude, direction, speed from c1 where ts > now-1d
```