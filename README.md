# 简介
经测试全区可用，能正常登入、点赞、浏览！

## 证书
* 安装根证书：[点击安装证书](https://github.com/Choler/Surge/raw/master/Thor%20SSL%20CA.cer)
* 信任根证书：手机设置-通用-关于本机-证书信任设置 打开按钮

## 规则
配置文件链接 `https://github.com/Choler/Surge/raw/master/Tiktok.conf`

### 必要
* Rewrite 和 MitM 开关同时打开
* 此时你就可以浏览正常Tiktok了

### 去水印
* 需要时打开抓取流量
* 最近的请求中都为缓存视频
* 点击请求链接再点响应 可查看视频内容
* 如需保存点击最下方Export 点击储存视频
* 此时视频就去水印保存到相册

```
[URL Rewrite]
(?<=&carrier_region=)CN(?=&is_my_cn=1) HK 307

[MITM]
hostname = *.tiktokv.com, *.byteoversea.com, *.musical.ly, *.snssdk.com, *.akamaized.net
```
