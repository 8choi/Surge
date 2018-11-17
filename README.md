# [URL Rewrite]
* Google复写
```
^http://www.google.cn http://www.google.com header
```
* 抖音视频下载去水印 `aweme.snssdk.com` 
```
(?<=&watermark=)1(?=.*) 0 302
```
* 屏蔽微博启动广告和正文推广 `api.weibo.cn` 
```
^http://u1.img.mobile.sina.cn/public/files/image/750x\d{4}.+(png|jpg|gif|mp4)$ - reject
^https://api.weibo.cn/2/statuses/extend\?gsid= - reject
^https://api.weibo.cn/2/statuses/longtext_show_batch - reject
```
* 屏蔽YouTube插播视频广告 `youtubei.googleapis.com`
```
^https://youtubei.googleapis.com/.+ad_break - reject
```
