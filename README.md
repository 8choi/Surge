# surge rule-set sample
### 完整的配置范例见 https://github.com/scomper/Surge/blob/master/surge3.conf
list 文件有两种获取方式，一种是本地，一种是远程，本地的 list 文件保存到 iCloud/Surge 目录下。

```
[Rule]

RULE-SET,SYSTEM,DIRECT

IP-CIDR,17.0.0.0/8,DIRECT,no-resolve

URL-REGEX,signed.beta.ipa,PROXY
URL-REGEX,signed.dpkg.ipa,DIRECT

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
