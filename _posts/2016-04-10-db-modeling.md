---
layout: post
title:  "joker数据建模"
categories: joker
---

* [对象(对电影，电视剧，动画和游戏的一层抽象，记录一些公共属性，并用来关联评论)](#Item)
* [电影](#movie)
* [电视剧](#tv-series)
* [动画](#animation)
* [游戏](#game)
* [人物](#person)
* [用户](#user)
* [评论](#comment)

## <a name="item"></a>对象 Item

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_ChineseName | 中文名 | `String` | Yes | null
_CoverPicture | 封面图 | `*File` | No
_Description | 描述 | `String` | No
_EnglishName | 英文名 | `String` | No
_OtherNames | 其他名字 | `Array[String]` | No
_Pictures | 截图 | `Array[*File]` | No
_Types | 类型 | `Array[String]` | No

## <a name="movie"></a>电影 Movie

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_Item | 对象 | `*Item` | Yes
_Actors | 演员表(人物: 角色) | `Object{*Person: String}` | No
_Awards | 得奖 | `Array[String]` | No
_ChinaDebutDate | 中国上映日期 | `Date` | No
_Countries | 国家 | `Array[String]` | No
_Director | 导演 | `Array[*Person]` | No
_Distributor | 发行公司 | `Array[String]` | No
_Duration | 时长(以ms为单位) | `Number` | No
_GlobalDebutDate | 全球首映日期 | `Date` | No
_Languages | 语言 | `Array[String]` | No
_Producer | 制作公司 | `Array[String]` | No
_Scores | 评分 | `Object{"db": Number, "imdb": Number, "rt": Number, "joker": Number}` | No
_Trailer | 预告片 | `String` | No
_Writer | 编剧 | `Array[*Person]` | No 

## <a name="tv-series"></a>电视剧 TVSeries

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_Item | 对象 | `*Item` | Yes
_Actors | 演员表(人物: 角色) | `Object{*Person: String}` | No
_Broadcaster | 播出公司 | `Array[String]` | No
_Countries | 国家 | `Array[String]` | No
_CurrentEpisode | 当前集数 | `Number` | No
_DayInTheWeek | 播出时间 | `String` | No
_DebutDate | 首播日期 | `Date` | No
_Director | 导演 | `Array[*Person]` | No
_Producer | 制作公司 | `Array[String]` | No
_Scores | 评分 | `Object{"db": Number, "imdb": Number, "rt": Number, "joker": Number}` | No
_TotalEpisodes | 集数 | `Number` | No
_Trailer | 预告片 | `String` | No
_Writer | 编剧 | `Array[*Person]` | No

## <a name="animation"></a>动画 Animation

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_Item | 对象 | `*Item` | Yes
_Actors | 声优(人物: 角色) | `Object{*Person: String}` | No
_Broadcaster | 播出公司 | `Array[String]` | No
_Countries | 国家 | `Array[String]` | No
_CurrentEpisode | 当前集数 | `Number` | No
_DayInTheWeek | 播出时间 | `String` | No
_DebutDate | 首播日期 | `Date` | No
_Director | 监督 | `Array[*Person]` | No
_Producer | 制作公司 | `Array[String]` | No
_Scores | 评分 | `Object{"db": Number, "imdb": Number, "rt": Number, "joker": Number}` | No
_TotalEpisodes | 集数 | `Number` | No
_Trailer | 预告片 | `String` | No
_Writer | 脚本 | `Array[*Person]` | No

## <a name="game"></a>游戏 Game
 
Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_Item | 对象 | `*Item` | Yes
_Distributor | 发行公司 | `Array[String]` | No
_Platforms | 游戏平台 | `Array[String]` | No
_Producer | 制作公司 | `Array[String]` | No
_ReleaseDates | 上市时间 | `Object{"cn": Date, "hk": Date, "jp": Date, "us": Date}` | No
_Scores | 评分 | `Object{"fami": Number, "ign": Number, "gs": Number, "joker": Number}` | No
_Trailer | 预告片 | `String` | No

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

## <a name="user"></a>用户 User

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_LikedAnimations | 喜欢的动画 | `Array[*Animation]` | No
_LikedGames | 喜欢的游戏 | `Array[*Game]` | No
_LikedMovies | 喜欢的电影 | `Array[*Movie]` | No
_LikedPerson | 喜欢的人物 | `Array[*Person]` | No
_LikedTVSeries | 喜欢的电视剧 | `Array[*TVSeries]` | No
_PlayedGames | 玩过的游戏 | `Array[*Game]` | No
_WantedAnimations | 想看的动画 | `Array[*Animation]` | No
_WantedGames | 想看的游戏 | `Array[*Game]` | No
_WantedMovies | 想看的电影 | `Array[*Movie]` | No
_WantedTVSeries | 想看的电视 | `Array[*TVSeries]` | No
_WatchedAnimations | 看过的动画 | `Array[*Animation]` | No
_WatchedMovies | 看过的电影 | `Array[*Movie]` | No
_WatchedTVSeries | 看过的电视 | `Array[*TVSeries]` | No

## <a name="comment"></a>评论 Comment

Column | Explain | Type | Required | Default
--- | --- | --- | --- | ---
_Author | 评论者 | `*User` | Yes
_Content | 评论内容 | `String` | No
_Item | 评论对象 | `*Item` | Yes
_Pictures | 评论插图 | `*File` | No
