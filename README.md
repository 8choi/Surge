# Rule-Set for Surge3

### Surge 官方lite文件配置范例，请参考 https://github.com/Blankwonder/surge-list

```
[Rule]

RULE-SET,SYSTEM,DIRECT

IP-CIDR,17.0.0.0/8,DIRECT,no-resolve

URL-REGEX,signed.beta.ipa,PROXY // TestFlight
URL-REGEX,signed.dpkg.ipa,DIRECT // App Store

DOMAIN-SUFFIX,me.com,PROXY
DOMAIN-SUFFIX,apple.co,PROXY
DOMAIN-SUFFIX,apple.com,DIRECT
DOMAIN-SUFFIX,icloud.com,PROXY
DOMAIN-SUFFIX,itunes.com,PROXY
DOMAIN-SUFFIX,aaplimg.com,PROXY
DOMAIN-SUFFIX,mzstatic.com,DIRECT
DOMAIN-SUFFIX,cdn-apple.com,DIRECT
DOMAIN-SUFFIX,icloud-content.com,PROXY

RULE-SET,https://github.com/Choler/Surge/raw/master/adblock.list,REJECT

RULE-SET,https://github.com/Choler/Surge/raw/master/telegram.list,PROXY

RULE-SET,LAN,DIRECT

GEOIP,CN,DIRECT,always-real-ip
FINAL,PROXY,dns-failed
