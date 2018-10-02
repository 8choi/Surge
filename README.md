# surge rule-set sample
### 官方surge.list配置范例 https://github.com/Blankwonder/surge-list

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
