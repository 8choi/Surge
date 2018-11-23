# 使用手册
* 安装并信任证书，确保 MitM 功能和 Rewrite 功能同时启用
* Surge：捷径 https://www.icloud.com/shortcuts/6da9a6c09618464d85c11580d81b1e51
* Quantumult：订阅 https://github.com/Choler/Surge/raw/master/Rejection.conf

## 常见问题
如何安装并信任证书?
```
安装：首页 - 配置根证书 - 安装证书
信任：设置 - 关于本机 - 证书信任设置 - 信任
```
主机名可以使用*通配符吗?
```
可以，但是由于进行 MitM 开销很大，请仅向需要的主机名启动。
```
为什么我用了你的规则之后还有启动广告?
```
由于先前广告已缓存到本地，一般清理缓存就可以，但部分应用需要卸载重装。
```

## [URL Rewrite]
* 
```
^http://www.google.cn http://www.google.com header
```
* 抖音视频下载去水印 `aweme.snssdk.com` 
```
(?<=&watermark=)1(?=.*) 0 302
```
* 拦截抖音短视频启动广告 `*ttcdn-tos.pstatp.com`
```
^https://sf\d-ttcdn-tos.pstatp.com/obj/web.business.image/ - reject
```
* 拦截微博启动广告和正文推广 `api.weibo.cn` 
```
^http://u1.img.mobile.sina.cn/public/files/image/\d{3}x\d{4}.+(png|jpg|gif|mp4)$ - reject
^https://api.weibo.cn/2/statuses/(extend\?gsid=|longtext_show_batch) - reject
```
* 拦截YouTube插播视频广告 `youtubei.googleapis.com`
```
^https://youtubei.googleapis.com/.+ad_break - reject
```
* 拦截腾讯视频开头视频广告 `lives.l.qq.com`
```
^https://lives.l.qq.com/livemsg\?sdtfrom= - reject
```
* 拦截京东金融启动广告和悬浮广告 `ms.jr.jd.com` `img*.360buyimg.com`
```
^https://ms.jr.jd.com/gw/generic/base/na/m/ad - reject
^https://img\d{1,}.360buyimg.com/jrpmobile/jfs/.+width=225&height=225$ - reject
```
* 拦截美团和美团外卖启动广告 `p*.meituan.net`
```
^https?://p\d.meituan.net/(mmc|wmbanner)/ - reject
```
* 拦截携程启动广告 `dimg*.c-ctrip.com` 
```
^https://dimg\d{2}.c-ctrip.com/images/.+_750_1334 - reject
```
* 拦截企鹅电竞启动广告
```
^http://shp.qpic.cn/pggamehead/.+new=1.0&w=1242&h=2208$ - reject
```
* 拦截招商银行启动广告 `pic1cdn.cmbchina.com`
```
^https://pic1cdn.cmbchina.com/appinitads/ - reject
```
* 拦截淘宝启动广告 `gw.alicdn.com`
```
^https://gw.alicdn.com/tfs/\w+-1125-1602 - reject
```
* 拦截京东启动广告和置顶宣传栏 `m.360buyimg.com`
```
^https://m.360buyimg.com/mobilecms/s(640x1136|750x1624|862x90)_jfs/ - reject
```
* 拦截网易云音乐启动广告 `p*.music.126.net`
```
^http://iadmusicmat.music.126.net/\w+.jpg$ - reject
^https?://p\d.music.126.net/\w+==/10995\d{13}.jpg$ - reject
```
* 拦截知乎启动广告和宣传广告 `api.zhihu.com`
```
^https://api.zhihu.com/(real_time_)?launch\?app= - reject
```
* 拦截滴滴出行启动广告 `img-*.didistatic.com`
```
^https://img-\w+.didistatic.com/static/zhuancheimg/image-1242-2208/.+.jpg$ - reject
```
* 拦截腾讯视频和腾讯新闻以及QQ音乐启动广告 `wa.gtimg.com`
```
^http://splashqqlive.gtimg.com/website/\d{6}/ - reject
^http://.*/vlive.qqvideo.tc.qq.com/.+.mp4 - reject
^https?://wa.gtimg.com/website/\d{6}/\w+_.{3} - reject
```
* 拦截掌上生活启动广告和悬浮广告 `mlife.cmbchina.com`
```
^https://mlife.cmbchina.com/ClientFace(Service)?/\w+Advertise(.+)?.json$ - reject
```
* 拦截饿了么启动广告 `fuss10.elemecdn.com`
```
^https://fuss10.elemecdn.com/.+/\d{3}/h/\d{4}/ - reject
```

### 关于
* 反馈 [Telegram](https://t.me/Bigbig_Choler)
* 打赏 [支付宝公益](https://love.alipay.com/donate/index.htm)

### 作者语
* 可以拷贝、转发，但不得用于商业用途。
