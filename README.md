Quantumt-X-Rules

Quantumult X rule sets automatically generated from upstream sources.

Usage

Add the following to [filter_remote] in Quantumult X:

https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/reject.txt, tag=Reject, force-policy=REJECT, update-interval=172800
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/proxy.txt, tag=Proxy, force-policy=PROXY, update-interval=172800
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/direct.txt, tag=Direct, force-policy=DIRECT, update-interval=172800
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/cncidr.txt, tag=China-IP, force-policy=DIRECT, update-interval=172800
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/telegramcidr.txt, tag=Telegram-IP, force-policy=PROXY, update-interval=172800

Rules

* proxy.txt — Proxy
* direct.txt — Direct
* reject.txt — Reject
* cncidr.txt — China IP
* telegramcidr.txt — Telegram IP
* gfw.txt — GFW
* greatfire.txt — GreatFire
* private.txt — Private
* icloud.txt — iCloud
* apple.txt — Apple
* google.txt — Google
* tld-not-cn.txt — Non-CN TLD

Rules are automatically updated by GitHub Actions.

Credits

Rule data is sourced from Loyalsoldier and felixonmars.

See the respective upstream repositories for licenses and attribution.