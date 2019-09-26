# 控制点管理系统

## 建立控制点数据库

管理控制（水准、GPS）点的大地坐标、基本信息与相关图片

### 水准点表结构

| 字段名        |   字段类型   |          说明 |
| ------------- | :----------: | ------------: |
| ID            |  AutoField   |          主键 |
| DJ            |  ForeignKey  |    水准点等级 |
| LXM           |  CharField   |        路线名 |
| pointname     |  CharField   |          点名 |
| SZD           |  CharField   |        所在地 |
| SZTF          |  CharField   |      所在图幅 |
| longitude     | DecimalField |   经度,DD格式 |
| latitude      | DecimalField |   纬度,DD格式 |
| locationimage |  ImageField  |    详细位置图 |
| BSLX          |  ForeignKey  |      标石类型 |
| BSZL          |  ForeignKey  |      标石质料 |
| BSDMT         |  ForeignKey  |    标石断面图 |
| TDSYZ         |  CharField   |    土地使用者 |
| JTLX          |  TextField   |      交通路线 |
| DXSSD         | DecimalField | 地下水深度(m) |
| DWXXSM        |  TextField   |  点位详细说明 |
| JGDW          |  CharField   |      接管单位 |
| BGR           |  CharField   |        保管人 |
| XDDW          |  CharField   |      选点单位 |
| XDZ           |  CharField   |        选点者 |
| XDRQ          |  DateField   |      选点日期 |
| MSDW          |  CharField   |      埋石单位 |
| MSZ           |  CharField   |        埋石者 |
| MSRQ          |  DateField   |      埋石日期 |
| WXDW          |  CharField   |      维修单位 |
| WXZ           |  CharField   |        维修者 |
| WXRQ          |  DateField   |      维修日期 |
| JJZP          |  ForeignKey  |      近景照片 |
| BZ            |  TextField   |          备注 |
| GC            | DecimalField |          高程 |

#### 水准点等级

| 字段名 | 字段类型  |       说明 |
| ------ | :-------: | ---------: |
| ID     | AutoField |       主键 |
| name   | CharField | 水准点等级 |

#### 标石类型

| 字段名 | 字段类型  |     说明 |
| ------ | :-------: | -------: |
| ID     | AutoField |     主键 |
| name   | CharField | 标石类型 |

#### 标石质料

| 字段名 | 字段类型  |     说明 |
| ------ | :-------: | -------: |
| ID     | AutoField |     主键 |
| name   | CharField | 标石质料 |

#### 标石断面图

| 字段名 |  字段类型  |       说明 |
| ------ | :--------: | ---------: |
| ID     | AutoField  |       主键 |
| image  | ImageField | 标石断面图 |

#### 近景照片

| 字段名     |  字段类型  |     说明 |
| ---------- | :--------: | -------: |
| ID         | AutoField  |     主键 |
| image      | ImageField | 近景照片 |
| levelpoint | ForeignKey |   水准点 |

### GPS点表结构

| 字段名    |   字段类型   |               说明 |
| --------- | :----------: | -----------------: |
| ID        |  AutoField   |               主键 |
| pointname |  CharField   |               点名 |
| pointnum  |  CharField   |               点号 |
| JB        |  ForeignKey  |               级别 |
| SZTF      |  CharField   |           所在图幅 |
| WQ        |  CharField   |               网区 |
| SZD       |  CharField   |             所在地 |
| ZJZSYJL   |  TextField   |     最近住所及距离 |
| DL        |  CharField   |               地类 |
| TZ        |  CharField   |               土质 |
| DTSD      | DecimalField |        冻土深度(m) |
| JDSD      | DecimalField |        解冻深度(m) |
| ZJDXSS    |  CharField   |       最近电信设施 |
| GDQK      |  CharField   |           供电情况 |
| ZJSYYJL   |  CharField   |     最近水源及距离 |
| SZLY1     |  CharField   |           石子来源 |
| SZLY2     |  CharField   |           沙子来源 |
| BDJTQK    |  TextField   |       本点交通情况 |
| JTLXT     |  ImageField  |         交通路线图 |
| XDDW      |  CharField   |           选点单位 |
| XDZ       |  CharField   |             选点者 |
| XDRQ      |  DateField   |           选点日期 |
| LCZBYGCQK |  CharField   | 联测坐标与高程情况 |
| LCDJYFF   |  CharField   |     联测等级与方法 |
| QSSZDJJL  |  TextField   |   起始水准点与距离 |
| DWLT      |  ImageField  |           点位略图 |
| DZGYGZBJ  |  TextField   | 地址概要、构造背景 |
| DXDZGZLT  |  ImageField  |   地形地质构造略图 |
| MSDW      |  CharField   |           埋石单位 |
| MSZ       |  CharField   |             埋石者 |
| MSRQ      |  DateField   |           埋石日期 |
| JDLYQK    |  CharField   |       旧点利用情况 |
| BSDMT     |  ForeignKey  |         标石断面图 |
| JSTXJHWZ  |  CharField   |   接受天线计划位置 |
| BSLX      |  ForeignKey  |           标石类型 |
| BSZL      |  ForeignKey  |           标石质料 |
| TDSYZ     |  CharField   |         土地使用者 |
| longitude | DecimalField |        经度,DD格式 |
| latitude  | DecimalField |        纬度,DD格式 |
| GC        | DecimalField |            高程(m) |
| JTLX      |  CharField   |           交通路线 |
| DWXXSM    |  TextField   |       点位详细说明 |
| JGDW      |  CharField   |           接管单位 |
| BGR       |  CharField   |             保管人 |
| BGRDWJZW  |  CharField   |   保管人单位及职务 |
| BGRZZ     |  CharField   |         保管人住址 |
| JJZP      |  ForeignKey  |           近景照片 |
| BZ        |  TextField   |               备注 |

#### GPS点等级

| 字段名 | 字段类型  |       说明 |
| ------ | :-------: | ---------: |
| ID     | AutoField |       主键 |
| name   | CharField | 水准点等级 |

#### GPS标石类型

| 字段名 | 字段类型  |     说明 |
| ------ | :-------: | -------: |
| ID     | AutoField |     主键 |
| name   | CharField | 标石类型 |

#### GPS标石质料

| 字段名 | 字段类型  |     说明 |
| ------ | :-------: | -------: |
| ID     | AutoField |     主键 |
| name   | CharField | 标石质料 |

#### GPS标石断面图

| 字段名 |  字段类型  |       说明 |
| ------ | :--------: | ---------: |
| ID     | AutoField  |       主键 |
| image  | ImageField | 标石断面图 |

#### GPS近景照片

| 字段名   |  字段类型  |     说明 |
| -------- | :--------: | -------: |
| ID       | AutoField  |     主键 |
| image    | ImageField | 近景照片 |
| GPSpoint | ForeignKey |    GPS点 |

## 导出控制点报告

### 水准点点之记

![](/readme/p3.png)

### GPS点点之记

![](/readme/p1.png)

![](/readme/p2.png)



## 二维码导航
导航二维码扫码后可利用具体的app导航比如百度地图、高德地图、腾讯地图进行选点导航。（是否要对扫一扫进行用户信息校验？如果进行校验需要布设服务器，不需要校验可以将点位信息硬编码至二维码中，直接使用系统自带的扫一扫功能即可打开相关的app）

### 地图API

#### 百度地图API
- [百度地图唤起API](http://lbsyun.baidu.com/index.php?title=uri)
:扫码可以在不同操作系统中唤起百度地图应用

#### 高德地图API
- [高德地图唤起API](https://lbs.amap.com/api/uri-api/gettingstarted)
:扫码可以在不同操作系统中唤起高德地图应用

#### 腾讯地图API
- [腾讯地图唤起API](https://lbs.qq.com/uri_v1/guide-mobile-navAndRoute.html)
:扫码可以在不同操作系统中唤起腾讯地图应用

### 创建二维码
输入GPS点或“水准点”后生成一个二维码，扫描二维码后用户可根据手机系统及软件选择自己要用的导航软件

## 项目参与者
- [uuiitwp](https://github.com/uuiitwp)
- [zyhqda](https://github.com/zyhqda)
