<!--
 * @file: readMe
 * @Author: luoquanquan
 * @Date: 2019-01-04 10:20:10
 * @LastEditors: luoquanquan
 * @LastEditTime: 2019-01-21 22:04:04
 -->
> 吃着火锅, 写着代码, 听着歌...一不小心某音乐就上市了. 趁着兴头扒了一套 api (极简, 可用, 从获取排行榜到歌曲播放 url, 歌词, 封面等信息). 现共享一下接口文档. 大家玩儿的开心. 😄

![2018-12-24-22-58-59](https://user-gold-cdn.xitu.io/2018/12/24/167e0d20c1822778?w=1120&h=472&f=png&s=827839)

## 诚邀共同维护者

由于个人的力量毕竟有限, 加之 🐧 厂的兄弟们一直致力于升级 api 上. 所以维护过程中出现心有余力不足的情况, 这里盛情邀请有精力且愿意折腾一下的小伙伴们和我一起来维护这个项目, 有兴趣的小伙伴请不吝提出 issue 和 PR.

![2019-01-06-16-05-29](http://img.blog.niubishanshan.top/2019-01-06-16-05-29.png)

## 本项目地址[github](https://github.com/luoquanquan/musicInterFace)

## 接口域名

> [music.niubishanshan.top](music.niubishanshan.top)

## basePath

> /api/v2/music

## 1. 获取首页推荐信息

### 1.1 功能描述

获取网站首页的推荐信息, 包含顶部轮播和广播

### 1.2 请求说明

> 请求说明: <br>
> 请求方式 GET<br>
> 请求URL ：[/recommend](https://music.niubishanshan.top/api/v2/music/recommend)

### 1.3 请求参数

字段 | 字段类型  | 字段说明
--- | --- | ---
无 | 无 | 无

### 1.4 返回结果

```json
{
    "announce": "本接口所有数据均来自 QQ 音乐, 仅供学习交流之用,请不要用于商业用途. 如果喜欢请下载 QQ 音乐 APP 畅听.如有侵权请联系微信(QQ): 1363693666, 我会第一时间删除~",
    "errno": 0,
    "msg": "success",
    "data": {
        "slider": [
            "http://y.gtimg.cn/music/common/upload/MUSIC_FOCUS/1121987.jpg",
            "http://y.gtimg.cn/music/common/upload/MUSIC_FOCUS/1122653.jpg",
            "http://y.gtimg.cn/music/common/upload/MUSIC_FOCUS/1121479.jpg",
            "http://y.gtimg.cn/music/common/upload/MUSIC_FOCUS/1120772.jpg",
            "http://y.gtimg.cn/music/common/upload/MUSIC_FOCUS/1123020.jpg"
        ],
        "radioList": [
            {
                "picUrl": "http://y.gtimg.cn/music/photo/radio/track_radio_199_13_1.jpg",
                "title": "热歌",
                "id": 199
            },
            {
                "picUrl": "http://y.gtimg.cn/music/photo/radio/track_radio_307_13_1.jpg",
                "title": "一人一首招牌歌",
                "id": 307
            }
        ]
    }
}
```

### 1.5 返回参数

字段 | 字段类型  | 字段说明
--- | --- | ---
announce | string | 声明文案
errno | int | 0: 表示没有问题, 其他表示有问题. 详情参考 msg
msg | string | 接口返回状态描述
data | object | 接口返回数据主体
&nbsp;&nbsp;slider | array | 轮播图信息(子条目为 string)
&nbsp;&nbsp;radioList | array | 电台列表数据(始终返回两条)
&nbsp;&nbsp;&nbsp;&nbsp;picUrl | string | 电台logo
&nbsp;&nbsp;&nbsp;&nbsp;title | string | 电台标题
&nbsp;&nbsp;&nbsp;&nbsp;id | ing | 电台id

qq音乐接口