# Elf 接口文档

## 目录

[TOC]

## 附加信息

> BaseUrl：`http://elf.egos.hosigus.com`

### 更新

* METHOD `GET`

* PATH `/getLastVersion.php`

* RETURN

  ```JSON
  {
      "status": 200,
      "message": "成功",
      "data": {
          "version": "beta 1.0"
      }
  }
  ```

### 心情歌单

* METHOD `GET`

* PATH `/getSongListID.php`

* PARAMETER

  `type: String`

  可取值有：**HAPPY**,**UNHAPPY**,**CLAM**,**EXCITING**

* RETURN

  ```JSON
  {
    "status": 200,
    "message": "成功",
    "data": {
        "id": 2332160280
    }
  }
  ```

### 推荐歌单

* METHOD `GET`

* PATH `/getRecommendID.php`

* RETURN

  ```JSON
  {
    "status": 200,
    "message": "成功",
    "data": {
        "id": 2336345537
    }
  }
  ```

## 音乐详情

> BaseUrl：`http://elf.egos.hosigus.com/music`

### 歌单信息

* METHOD `POST`

* Content-Type `application/x-www-form-urlencoded`

* PATH `/playlist/detail`

* PARAMETER

  `id: Long`

* RETURN

> 已提取关键部分，类似JSON已省略

  ```JSON
  {
    "code": 200,
    "playlist":{
      "tracks":[
        {
          "name": "歌曲名字",
          "id": 424060342,
          "ar": [
            {
                "id": 0,
                "name": "作者名字"
            }
          ],
          "al": {
            "id": 3358040,
            "name": "所在专辑名字",
            "picUrl": "http://p2.music.126.net/7VNhKpCYVz3UWAATV_HstA==/109951163828297300.jpg"
          }
        },...
      ],
      "trackIds":[
        {
          "id": 424060342
        },...
      ],
      "coverImgUrl": "http://p1.music.126.net/05xtHVg_0G3fFWVjJciexA==/109951163897711683.jpg",
      "description": "歌单描述...",
      "name": "歌单名字"
    }
  }
  ```

### 歌曲文件

拼接URL即可：

`http://music.163.com/song/media/outer/url?id=$id.mp3`

注: 将此处`$id`替换为目标音乐id

例：`http://music.163.com/song/media/outer/url?id=424060342.mp3`

### 歌词

* METHOD `POST`

* Content-Type `application/x-www-form-urlencoded`

* PATH `/lyric`

* PARAMETER

  `id: Long`

* RETURN

  ```JSON
  {
    "lrc": {
        "version": 6,
        "lyric": "..."
    },
    "code": 200
  }
  ```

## 附录

Postman 分享链接：https://www.getpostman.com/collections/3a8a8816e60b88b0c2cb