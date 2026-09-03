Quantumt-X-Rules

Usage Example (filter_remote)

###Proxy Policy is just an example policy group name. Replace it with the policy group name you actually use in Quantumult X

```ini
[filter_remote]
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/icloud.txt, tag=iCloud, force-policy=direct, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/apple.txt, tag=Apple, force-policy=direct, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/proxy.txt, tag=Proxy, force-policy=Proxy Policy, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/dmulle12/Quantumt-X-Rules/release/ruleset/direct.txt, tag=Direct, force-policy=direct, update-interval=172800, opt-parser=false, enabled=true
FILTER_LAN, tag=LAN, force-policy=direct, enabled=true
FILTER_REGION, tag=CN, force-policy=direct, enabled=true
```

Rules are automatically updated by GitHub Actions.