# [URL Rewrite]
* Google复写
```
^http://www.google.cn http://www.google.com header
```
* 抖音视频下载去水印 `aweme.snssdk.com` 
```
(?<=&watermark=)1(?=.*) 0 302
```
* 拦截微博启动广告和正文页广告 `api.weibo.cn` 
```
^http://u1.img.mobile.sina.cn/public/files/image/\d{3}x\d{4}.+(png|jpg|gif|mp4)$ - reject
^https://api.weibo.cn/2/statuses/(extend\?gsid=|longtext_show_batch) - reject
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
* 拦截携程启动广告 `dimg*.c-ctrip.com` 
```
^https://dimg\d{2}.c-ctrip.com/images/.+_750_1334 - reject
```
* 拦截企鹅电竞启动广告
```
^http://shp.qpic.cn/pggamehead/.+new=1.0&w=1242&h=2208$ - reject
```
* 拦截腾讯视频启动广告和开头视频广告 `lives.l.qq.com`
```
^http://splashqqlive.gtimg.com/website/\d{6}/ - reject
^https://lives.l.qq.com/livemsg\?sdtfrom= - reject
```
* 拦截招商银行启动广告 `pic1cdn.cmbchina.com`
```
^https://pic1cdn.cmbchina.com/appinitads/ - reject
```
* 拦截QQ音乐启动广告 `wa.gtimg.com`
```
^https://wa.gtimg.com/website/\d{6}/\w+_.{3} - reject
```
* 拦截淘宝启动广告 `gw.alicdn.com`
```
^https://gw.alicdn.com/tfs/\w+-1125-1602 - reject
```
* 拦截京东启动广告和置顶宣传栏 `m.360buyimg.com`
```
^https://m.360buyimg.com/mobilecms/s(640x1136|750x1624|862x90)_jfs/ - reject
```
