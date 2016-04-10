---
layout: post
title:  "joker数据建模"
categories: joker
---

* [电影](#movie)
* [电视剧](#tv-series)
* [动画](#animation)
* [游戏](#game)
* [人物](#person)

## <a name="movie"></a>电影 Movie

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_Actors | 演员表(人物: 角色) | `Object{*Person: String}` | No
_Awards | 得奖 | `Array[String]` | No
_ChinaDebutDate | 中国上映日期 | `Date` | No
_ChineseName | 中文电影名 | `String` | Yes | null
_Countries | 国家 | `Array[String]` | No
_CoverPicture | 封面图 | `*File` | No
_Description | 描述 | `String` | No
_Director | 导演 | `Array[*Person]` | No
_Distributor | 发行公司 | `Array[String]` | No
_Duration | 时长(以ms为单位) | `Number` | No
_EnglishName | 英文电影名 | `String` | No
_GlobalDebutDate | 全球首映日期 | `Date` | No
_Languages | 语言 | `Array[String]` | No
_OtherNames | 其他名字 | `Array[String]` | No
_Pictures | 截图 | `Array[*File]` | No
_Producer | 制作公司 | `Array[String]` | No
_Scores | 评分 | `Object{"db": Number, "imdb": Number, "rt": Number, "joker": Number}` | No
_Trailer | 预告片 | `String` | No
_Types | 类型 | `Array[String]` | No
_Writer | 编剧 | `Array[*Person]` | No 

## <a name="tv-series"></a>电视剧 TVSeries

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_Actors | 演员表(人物: 角色) | `Object{*Person: String}` | No
_Broadcaster | 播出公司 | `Array[String]` | No
_ChineseName | 中文剧名 | `String` | Yes | null
_Countries | 国家 | `Array[String]` | No
_CoverPicture | 封面图 | `*File` | No
_CurrentEpisode | 当前集数 | `Number` | No
_DayInTheWeek | 播出时间 | `String` | No
_DebutDate | 首播日期 | `Date` | No
_Description | 描述 | `String` | No
_Director | 导演 | `Array[*Person]` | No
_EnglishName | 英文剧名 | `String` | No
_OtherNames | 其他名字 | `Array[String]` | No
_Pictures | 截图 | `Array[*File]` | No
_Producer | 制作公司 | `Array[String]` | No
_Scores | 评分 | `Object{"db": Number, "imdb": Number, "rt": Number, "joker": Number}` | No
_TotalEpisodes | 集数 | `Number` | No
_Trailer | 预告片 | `String` | No
_Types | 类型 | `Array[String]` | No
_Writer | 编剧 | `Array[*Person]` | No

## <a name="animation"></a>动画 Animation

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_Actors | 声优(人物: 角色) | `Object{*Person: String}` | No
_Broadcaster | 播出公司 | `Array[String]` | No
_ChineseName | 中文动画名 | `String` | Yes | null
_Countries | 国家 | `Array[String]` | No
_CoverPicture | 封面图 | `*File` | No
_CurrentEpisode | 当前集数 | `Number` | No
_DayInTheWeek | 播出时间 | `String` | No
_DebutDate | 首播日期 | `Date` | No
_Description | 描述 | `String` | No
_Director | 监督 | `Array[*Person]` | No
_EnglishName | 英文动画名 | `String` | No
_OtherNames | 其他名字 | `Array[String]` | No
_Pictures | 截图 | `Array[*File]` | No
_Producer | 制作公司 | `Array[String]` | No
_Scores | 评分 | `Object{"db": Number, "imdb": Number, "rt": Number, "joker": Number}` | No
_TotalEpisodes | 集数 | `Number` | No
_Trailer | 预告片 | `String` | No
_Types | 类型 | `Array[String]` | No
_Writer | 脚本 | `Array[*Person]` | No

## <a name="game"></a>游戏 Game
 
Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_ChineseName | 中文游戏名 | `String` | Yes | null
_CoverPicture | 封面图 | `*File` | No
_Description | 描述 | `String` | No
_Distributor | 发行公司 | `Array[String]` | No
_EnglishName | 英文游戏名 | `String` | No
_OtherNames | 其他名字 | `Array[String]` | No
_Pictures | 截图 | `Array[*File]` | No
_Platforms | 游戏平台 | `Array[String]` | No
_Producer | 制作公司 | `Array[String]` | No
_ReleaseDates | 上市时间 | `Object{"cn": Date, "hk": Date, "jp": Date, "us": Date}` | No
_Scores | 评分 | `Object{"fami": Number, "ign": Number, "gs": Number, "joker": Number}` | No
_Trailer | 预告片 | `String` | No
_Types | 类型 | `Array[String]` | No

## <a name="person"></a>人物 Person

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_Awards | 得奖 | `Array[String]` | No
_ChineseName | 中文名字 | `String` | Yes | null
_DateOfBirth | 出生日期 | `Date` | No  
_DateOfDeath | 逝世日期 | `Date` | No 
_EnglishName | 英文名字 | `String` | No
_Nationality | 国籍 | `String` | No
_OtherNames | 其他名字 | `Array[String]` | No
_Picture | 头像 | `*File` | No
_Types | 身份 | `Array[String]` | No
