# [URL Rewrite]
* Google复写
```
^http://www.google.cn http://www.google.com header
```
* 抖音视频下载去水印 `aweme.snssdk.com` 
```
(?<=&watermark=)1(?=.*) 0 302
```
* 拦截微博开屏启动和正文推广 `api.weibo.cn` 
```
^http://u1.img.mobile.sina.cn/public/files/image/750x\d{4}.+(png|jpg|gif|mp4)$ - reject
^https://api.weibo.cn/2/statuses/extend\?gsid= - reject
^https://api.weibo.cn/2/statuses/longtext_show_batch - reject
```
* 拦截YouTube插播视频广告 `youtubei.googleapis.com`
```
^https://youtubei.googleapis.com/.+ad_break - reject
```
* 拦截京东金融启动广告和悬浮广告 `img12.360buyimg.com`
```
^https://img\d{1,}.360buyimg.com/(pop|jrpmobile)/jfs/.+.jpg - reject
^https://img\d{1,}.360buyimg.com/jrpmobile/jfs/.+width=225&height=225$ - reject
```
