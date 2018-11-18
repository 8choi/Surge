# [URL Rewrite]
* Google复写
```
^http://www.google.cn http://www.google.com header
```
* 抖音视频下载去水印 `aweme.snssdk.com` 
```
(?<=&watermark=)1(?=.*) 0 302
```
* 拦截微博启动广告和正文推广 `api.weibo.cn` 
```
^http://u1.img.mobile.sina.cn/public/files/image/750x\d{4}.+(png|jpg|gif|mp4)$ - reject
^https://api.weibo.cn/2/statuses/extend\?gsid= - reject
^https://api.weibo.cn/2/statuses/longtext_show_batch - reject
```
* 拦截YouTube插播视频广告 `youtubei.googleapis.com`
```
^https://youtubei.googleapis.com/.+ad_break - reject
```
* 拦截京东金融启动广告和悬浮广告 `ms.jr.jd.com` `img*.360buyimg.com`
```
^https://ms.jr.jd.com/gw/generic/base/na/m/ad - reject
^https://img\d{1,}.360buyimg.com/jrpmobile/jfs/.+width=225&height=225$ - reject
```
* 拦截美团和美团外卖启动广告 `p*.meituan.net`
```
^https?://p\d{1}.meituan.net/(mmc|wmbanner)/ - reject
```
