<head><meta charset="UTF-8"></head><pre style="caret-color: rgb(0, 0, 0); color: rgb(0, 0, 0); font-style: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: auto; text-align: start; text-indent: 0px; text-transform: none; widows: auto; word-spacing: 0px; -webkit-tap-highlight-color: rgba(26, 26, 26, 0.3); -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px; text-decoration: none; overflow-wrap: break-word; white-space: pre-wrap;"># ShadowRocket-懒人配置基础版
#【作者】w37fhy 【电报频道】https://t.me/w37fhy【更新日期】2022/11/10
#【YouTube视频教程】 ShadowRocket小火箭教程：https://youtu.be/E64XnxgitOc
#【大飛自用机场一】http://bit.ly/3hqNSW4 (推荐购买套餐180/年/月含150G流量)
#【大飛自用机场二】http://bit.ly/3Eh1aBy (推荐购买套餐145/季/共含1500GB流量)

[General]
bypass-system = true
skip-proxy = 192.168.0.0/16, 10.0.0.0/8, 172.16.0.0/12, localhost, *.local, captive.apple.com
tun-excluded-routes = 10.0.0.0/8, 100.64.0.0/10, 127.0.0.0/8, 169.254.0.0/16, 172.16.0.0/12, 192.0.0.0/24, 192.0.2.0/24, 192.88.99.0/24, 192.168.0.0/16, 198.51.100.0/24, 203.0.113.0/24, 224.0.0.0/4, 255.255.255.255/32, 239.255.255.250/32
dns-server = 114.114.114.114, 223.5.5.5, 119.29.29.29
ipv6 = false
prefer-ipv6 = false
dns-fallback-system = false
dns-direct-system = false
icmp-auto-reply = true
always-reject-url-rewrite = false
private-ip-answer = true
# direct domain fail to resolve use proxy rule
dns-direct-fallback-proxy = true


[Proxy Group]
🚀 节点选择 = select,♻️ 自动选择,🇭🇰 香港节点,🇨🇳 台湾节点,🇯🇵 日本节点,🇰🇷 韩国节点,🇸🇬 新加坡节点,🇺🇲 美国节点,REJECT,DIRECT,interval=600,timeout=5,select=1,url=http://www.gstatic.com/generate_204
👋 手动切换 = select, interval=600, timeout=5, select=0, url=http://www.gstatic.com/generate_204, policy-regex-filter=*
♻️ 自动选择 = url-test,url=http://www.gstatic.com/generate_204,interval=600,tolerance=80,timeout=5,select=0,policy-regex-filter=*
🇭🇰 香港节点 = url-test, interval=600, tolerance=80, timeout=5, select=0, url=http://www.gstatic.com/generate_204, policy-regex-filter=(?=.*(港|HK|(?i)Hong))^((?!(台湾|日本|新加坡|美国|韩国|狮城|南朝鲜|US|SG|JP|KR|TW|台灣|美國|韓國|獅城)).)*$
🇨🇳 台湾节点 = url-test, interval=600, tolerance=80, timeout=5, select=0, url=http://www.gstatic.com/generate_204, policy-regex-filter=(?=.*(台|TW|(?i)Taiwan))^((?!(港|日|韩|新|美)).)*$
🇯🇵 日本节点 = url-test, interval=600, tolerance=80, timeout=5, select=0, url=http://www.gstatic.com/generate_204, policy-regex-filter=(?=.*(日本|JP|(?i)Japan))^((?!(香港|台湾|新加坡|美国|韩国|狮城|南朝鲜|US|SG|KR|HK|TW|台灣|美國|韓國|獅城)).)*$
🇰🇷 韩国节点 = url-test, interval=600, tolerance=100, timeout=5, select=0, url=http://www.gstatic.com/generate_204, policy-regex-filter=(?=.*(KR|Korea|KOR|首尔|韩|韓|(?i)Korea))^((?!(香港|台湾|新加坡|美国|狮城|南朝鲜|US|SG|HK|TW|台灣|美國|獅城)).)*$
🇸🇬 新加坡节点 = url-test, interval=600, tolerance=100, timeout=5, select=0, url=http://www.gstatic.com/generate_204, policy-regex-filter=(?=.*(新加坡|狮城|SG|(?i)Singapore))^((?!(香港|台湾|日本|美国|韩国|南朝鲜|US|JP|KR|HK|TW|台灣|美國|韓國)).)*$
🇺🇲 美国节点 = url-test, interval=600, tolerance=100, timeout=5, select=0, url=http://www.gstatic.com/generate_204, policy-regex-filter=(?=.*(美国|美國|US|洛杉矶|西雅图|(?i)States|American))^((?!(香港|台湾|日本|新加坡|韩国|狮城|南朝鲜|SG|JP|KR|HK|TW|台灣|韓國|獅城)).)*$
🎵 TikTok节点 = select, 🇨🇳 台湾节点, 🇯🇵 日本节点, 🇰🇷 韩国节点, 🇺🇲 美国节点, DIRECT, interval=600, timeout=5, select=0, url=http://www.gstatic.com/generate_204
🐟 漏网之鱼 = select, 🚀 节点选择, ♻️ 自动选择, 🇭🇰 香港节点, 🇨🇳 台湾节点, 🇯🇵 日本节点, 🇰🇷 韩国节点, 🇸🇬 新加坡节点, 🇺🇲 美国节点, REJECT, DIRECT, interval=600, timeout=5, select=0, url=http://www.gstatic.com/generate_204

[Rule]
# TikTok分流
RULE-SET,https://raw.githubusercontent.com/Semporia/TikTok-Unlock/master/Shadowrocket/TikTok.list,🎵 TikTok节点
# 后续规则修正
RULE-SET,https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Filter/Unbreak.list,DIRECT
# 轻量广告拦截
RULE-SET,https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Filter/Guard/Advertising.list,REJECT
# 隐私追踪
RULE-SET,https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Filter/Guard/Privacy.list,REJECT
# 运营商劫持或恶意网站
RULE-SET,https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Filter/Guard/Hijacking.list,REJECT
# 流媒体服务
RULE-SET,https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Filter/StreamingMedia/Streaming.list,🚀 节点选择
# 国际网络分流
RULE-SET,https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Filter/Global.list,🚀 节点选择
# 国内网络分流
RULE-SET,https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Filter/China.list,DIRECT
#规则之外
GEOIP,CN,DIRECT
FINAL,🐟 漏网之鱼</pre>
DOMAIN-SUFFIX,silversingles.com,PROXY
DOMAIN-SUFFIX,eiltesingles.com,PROXY
