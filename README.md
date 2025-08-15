# 哔哩哔哩规则

```
rule-providers:
  # 全部分流
#  bilibili:
#    type: http
#    behavior: classical
#    url: https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Clash/BiliBili/BiliBili.yaml
#    interval: 86400
  # ip归属地
  bilibili-ip:
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/elysias123/bilibili-iplocation-rule/refs/heads/main/bilibili.yaml
    interval: 86400
  # pcdn
  bilibili-pcdn:
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/elysias123/bilibili-iplocation-rule/refs/heads/main/bilibili-pcdn.yaml
    interval: 86400


rules:
  - DOMAIN,upos-hz-mirrorakam.akamaized.net,REJECT # 屏蔽海外upos 防止视频走代理
  - RULE-SET,bilibili-pcdn,REJECT
  - RULE-SET,bilibili-ip,proxy
# - RULE-SET,bilibili,DIRECT # 如果视频还是走代理，请强制让剩余bilibili流量全部走直连

```
