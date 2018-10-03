# Rule-Set for Surge3

### Surge 官方lite文件配置范例，请参考 https://github.com/Blankwonder/surge-list
### Surge 的几种策略配置规范，请参考 https://manual.nssurge.com/policy/proxy.html
### Surge 现已支持 UDP 转发功能，请参考: https://trello.com/c/ugOMxD3u/53-udp-%E8%BD%AC%E5%8F%91
### Surge 现已支持 TCP-Fast-Open 技术，请参考: https://trello.com/c/ij65BU6Q/48-tcp-fast-open-troubleshooting-guide
### Surge 现已支持 ss-libev 的全部加密方式和混淆，请参考: https://trello.com/c/BTr0vG1O/47-ss-libev-%E7%9A%84%E6%94%AF%E6%8C%81%E6%83%85%E5%86%B5

```
[Rule]

RULE-SET,SYSTEM,DIRECT

IP-CIDR,17.0.0.0/8,DIRECT,no-resolve

URL-REGEX,signed.beta.ipa,PROXY // App Store
URL-REGEX,signed.dpkg.ipa,DIRECT // TestFlight

DOMAIN-SUFFIX,me.com,PROXY
DOMAIN-SUFFIX,apple.co,PROXY
DOMAIN-SUFFIX,apple.com,DIRECT
DOMAIN-SUFFIX,icloud.com,PROXY
DOMAIN-SUFFIX,itunes.com,PROXY
DOMAIN-SUFFIX,aaplimg.com,PROXY
DOMAIN-SUFFIX,mzstatic.com,DIRECT
DOMAIN-SUFFIX,cdn-apple.com,DIRECT
DOMAIN-SUFFIX,icloud-content.com,PROXY
DOMAIN-SUFFIX,lookup-api.apple.com,PROXY

RULE-SET,https://github.com/Choole/Surge/raw/master/adblock.list,REJECT

RULE-SET,https://github.com/Choole/Surge/raw/master/telegram.list,PROXY

RULE-SET,LAN,DIRECT

GEOIP,CN,DIRECT
FINAL,PROXY,dns-failed
