---
layout: splash
header:
  teaser: /image/post-infovis-02.jpg
  overlay_image: /assets/images/bg_tree_1.jpg
  overlay_filter: rgba(64,224,208, 0.5)
  image_description: "Waldeinsamkeit 置身森林深处,与自然水乳交融的孤独"
  cta_label: "More Info"
  cta_url: "https://unsplash.com"
title:  "[未完]tableau  生成和使用地图"
excerpt: "tableau教程文档  生成和使用地图"
author: treeice
categories: posts infovis
---
##### [来源](http://onlinehelp.tableau.com/current/pro/desktop/zh-cn/help.htm#buildexamples_maps.html)

### 一.[Tableau 支持的郡/县同级别地区](http://onlinehelp.tableau.com/current/pro/desktop/zh-cn/help.htm#maps_data.html%3FTocPath%3D%25E8%25AE%25BE%25E8%25AE%25A1%25E8%25A7%2586%25E5%259B%25BE%25E5%2592%258C%25E5%2588%2586%25E6%259E%2590%25E6%2595%25B0%25E6%258D%25AE%7C%25E7%2594%259F%25E6%2588%2590%25E5%2592%258C%25E4%25BD%25BF%25E7%2594%25A8%25E5%259C%25B0%25E5%259B%25BE%7C%25E5%25B0%2586%25E4%25BD%258D%25E7%25BD%25AE%25E6%2595%25B0%25E6%258D%25AE%25E5%25BC%2595%25E5%2585%25A5%25E5%2588%25B0%2520Tableau%7C_____1	)

 - 支持全球机场代码、城市、国家、地区、领地、州、省和一些邮政编码和二级行政区（县同级别地区）
 - 支持美国地区代码、核心基础统计区域 (CBSA)、都市统计区域 (MSA)、国会选区和邮政编码
 - 支持任何纬度和经度坐标 ,**十进制度数**

### 二.[在 Tableau 不能识别您的地理数据的情况下该怎么办](http://onlinehelp.tableau.com/current/pro/desktop/zh-cn/help.htm#maps_geographicroles.html%3FTocPath%3D%25E8%25AE%25BE%25E8%25AE%25A1%25E8%25A7%2586%25E5%259B%25BE%25E5%2592%258C%25E5%2588%2586%25E6%259E%2590%25E6%2595%25B0%25E6%258D%25AE%7C%25E7%2594%259F%25E6%2588%2590%25E5%2592%258C%25E4%25BD%25BF%25E7%2594%25A8%25E5%259C%25B0%25E5%259B%25BE%7C%25E5%25B0%2586%25E4%25BD%258D%25E7%25BD%25AE%25E6%2595%25B0%25E6%258D%25AE%25E5%25BC%2595%25E5%2585%25A5%25E5%2588%25B0%2520Tableau%7C_____2)	

 - 手动为字段分配地理角色   **Tableau 支持您的位置数据**
 - 导入自定义地理编码数据	**Tableau Desktop 版本 10.2 及更高版本上才支持**
 
### 三.[依据空间文件创建 Tableau 地图](http://onlinehelp.tableau.com/current/pro/desktop/zh-cn/help.htm#maps_shapefiles.html%3FTocPath%3D%25E8%25AE%25BE%25E8%25AE%25A1%25E8%25A7%2586%25E5%259B%25BE%25E5%2592%258C%25E5%2588%2586%25E6%259E%2590%25E6%2595%25B0%25E6%258D%25AE%7C%25E7%2594%259F%25E6%2588%2590%25E5%2592%258C%25E4%25BD%25BF%25E7%2594%25A8%25E5%259C%25B0%25E5%259B%25BE%7C%25E5%25B0%2586%25E4%25BD%258D%25E7%25BD%25AE%25E6%2595%25B0%25E6%258D%25AE%25E5%25BC%2595%25E5%2585%25A5%25E5%2588%25B0%2520Tableau%7C_____3)

 > **空间文件类型：Shapefile、MapInfo 表、KML（锁眼标记语言）文件以及 GeoJSON 文件。**
 
 > **Tableau Desktop 版本 10.2 和更高版本中支持**
 
 - 连接到空间文件
 - 1. **新建数据源”图标”，并选择“空间文件“**
 - 2. 所有数据都会转换为 WGS84 (EPSG:4326)。**确保文件采用 UTF-8 编码**
 - 3. 例子
 - - - [LONDON DATASTORE](https://data.london.gov.uk/dataset/statistical-gis-boundary-files-london)
 - - - [EGIS South Africa](http://egis.environment.gov.za/Download.aspx?m=25)
 - - - [U.S. Energy Information Administration](https://www.eia.gov/maps/maps.htm#geodata)
 - - - [USGS Water Resources](http://water.usgs.gov/maps.html)
 - - - [Geospatial Information Authority of Japan](http://www.gsi.go.jp/kankyochiri/gm_japan_e.html)
 - - - [Data.gov](https://www.data.gov/) 
 - - - [Census.gov](http://www.census.gov/geo/maps-data/)
 - 大型空间数据集的视图需要长时间呈现。使用筛选器
 - 自定义几何图形的外观，颜色，外观，线条
 - 依据空间数据构建双轴地图
 
 ## 四.自定义您的数据地理编码
 
 - 使用位置数据创建 CSV 文件
 - 1. 文件必须包含“Latitude”和“Longitude”列。
 - 2. Latitude 和 Longitude 值必须是实数。包含至少一个小数位
 - 3. 扩展现有的分层地理角色
 -
 -
 - 
 
 
 
 
 