##### 𝐐𝐮𝐚𝐧𝐭𝐮𝐦𝐭-𝐗-𝐑𝐮𝐥𝐞𝐬

###### Usage Example (filter_remote)

###### 𝗣𝗿𝗼𝘅𝘆 𝗣𝗼𝗹𝗶𝗰𝘆 𝗶𝘀 𝗷𝘂𝘀𝘁 𝗮𝗻 𝗲𝘅𝗮𝗺𝗽𝗹𝗲 𝗽𝗼𝗹𝗶𝗰𝘆 𝗴𝗿𝗼𝘂𝗽 𝗻𝗮𝗺𝗲. 𝗥𝗲𝗽𝗹𝗮𝗰𝗲 𝗶𝘁 𝘄𝗶𝘁𝗵 𝘁𝗵𝗲 𝗽𝗼𝗹𝗶𝗰𝘆 𝗴𝗿𝗼𝘂𝗽 𝗻𝗮𝗺𝗲 𝘆𝗼𝘂 𝗮𝗰𝘁𝘂𝗮𝗹𝗹𝘆 𝘂𝘀𝗲 𝗶𝗻 𝗤𝘂𝗮𝗻𝘁𝘂𝗺𝘂𝗹𝘁 𝗫

```ini
[filter_remote]
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/icloud.txt, tag=iCloud, force-policy=direct, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/apple.txt, tag=Apple, force-policy=direct, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/proxy.txt, tag=Proxy, force-policy=Proxy Policy, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/direct.txt, tag=Direct, force-policy=direct, update-interval=172800, opt-parser=false, enabled=true
FILTER_LAN, tag=LAN, force-policy=direct, enabled=true
FILTER_REGION, tag=CN, force-policy=direct, enabled=true
```
##### Rules are automatically updated by GitHub Actions.