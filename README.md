# Rule-Set for Surge3

### Surge 官方lite文件配置范例，请参考 https://github.com/Blankwonder/surge-list

```
[Rule]

RULE-SET,SYSTEM,DIRECT

RULE-SET,LAN,DIRECT

RULE-SET,https://github.com/Choler/Surge/raw/master/AdBlock.list,REJECT

RULE-SET,https://github.com/Choler/Surge/raw/master/iCloud.list,PROXY

RULE-SET,https://github.com/Choler/Surge/raw/master/Telegram.list,PROXY

RULE-SET,https://github.com/Choler/Surge/raw/master/AppStore.list,DIRECT

RULE-SET,https://github.com/Choler/Surge/raw/master/GeoIP-CN.list,DIRECT

FINAL,PROXY,dns-failed