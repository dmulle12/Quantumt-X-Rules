# Quantumult-X-Rules

Quantumult X filter rules, automatically generated every day by GitHub Actions.

**Sources**

- [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) — direct / proxy / reject / gfw / greatfire
- [Loyalsoldier/domain-list-custom](https://github.com/Loyalsoldier/domain-list-custom) — icloud / private / tld-!cn
- [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) — cn / telegram IP ranges
- [felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list) — apple / google (China-reachable)

**How it works**: every day at 22:30 UTC the workflow converts the upstream lists into QX filter format, force-pushes them to the [`release`](https://github.com/dmulle12/Quantumult-X-Rules/tree/release) branch, and purges the jsDelivr cache. Upstream `regexp:` entries become `HOST-REGEX`, `keyword:` entries become `HOST-KEYWORD` — nothing is silently dropped.

## Usage

In Quantumult X go to Settings → Filter → Remote, and add the lists you need.
`update-interval=86400` refreshes them once a day.

### Lists with embedded policy (no `force-policy` needed)

These files already carry `direct` / `proxy` / `reject`, so they work with QX built-in policies out of the box.
Add `force-policy=YourGroup` only if you want them routed through your own policy group instead.

```ini
[filter_remote]
https://cdn.jsdelivr.net/gh/dmulle12/Quantumult-X-Rules@release/ruleset/reject.txt, tag=AdBlock, update-interval=86400, opt-parser=false, enabled=true
https://cdn.jsdelivr.net/gh/dmulle12/Quantumult-X-Rules@release/ruleset/direct.txt, tag=Direct, update-interval=86400, opt-parser=false, enabled=true
https://cdn.jsdelivr.net/gh/dmulle12/Quantumult-X-Rules@release/ruleset/proxy.txt, tag=Proxy, update-interval=86400, opt-parser=false, enabled=true
```

### Lists without embedded policy (`force-policy` required)

`icloud.txt`, `apple.txt` and `google.txt` carry no policy column, so you must set one:

```ini
[filter_remote]
https://cdn.jsdelivr.net/gh/dmulle12/Quantumult-X-Rules@release/ruleset/icloud.txt, tag=iCloud, force-policy=direct, update-interval=86400, opt-parser=false, enabled=true
https://cdn.jsdelivr.net/gh/dmulle12/Quantumult-X-Rules@release/ruleset/apple.txt, tag=Apple, force-policy=direct, update-interval=86400, opt-parser=false, enabled=true
https://cdn.jsdelivr.net/gh/dmulle12/Quantumult-X-Rules@release/ruleset/google.txt, tag=GoogleCN, force-policy=direct, update-interval=86400, opt-parser=false, enabled=true
```

You can also use the built-in shortcuts instead of remote lists for LAN / region:

```ini
[filter_remote]
FILTER_LAN, tag=LAN, force-policy=direct, enabled=true
FILTER_REGION, tag=CN, force-policy=direct, enabled=true
```

## Full rule list

| File | Content | Policy |
|---|---|---|
| `reject.txt` | Ads & trackers (~190k) | `reject` (embedded) |
| `direct.txt` | Direct domains (~110k) | `direct` (embedded) |
| `proxy.txt` | Proxy domains (~27k) | `proxy` (embedded) |
| `gfw.txt` | GFW list domains | `proxy` (embedded) |
| `greatfire.txt` | GreatFire domains | `proxy` (embedded) |
| `tld-not-cn.txt` | Non-CN top-level domains | `proxy` (embedded) |
| `private.txt` | Private / intranet domains | `direct` (embedded) |
| `cncidr.txt` | China IPv4/IPv6 ranges | `direct` (embedded) |
| `telegramcidr.txt` | Telegram IP ranges | `proxy` (embedded) |
| `icloud.txt` | iCloud domains | `force-policy` required (suggest `direct`) |
| `apple.txt` | Apple domains reachable in China | `force-policy` required (suggest `direct`) |
| `google.txt` | Google domains reachable in China | `force-policy` required (suggest `direct`) |

Suggested order in QX: reject → direct → proxy, then `FINAL` to your default policy.

## License

MIT
