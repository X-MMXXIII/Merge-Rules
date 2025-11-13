# Merge Rules

![Python Version](https://img.shields.io/badge/Python-3%2B-blue?)
![Build Status](https://img.shields.io/github/actions/workflow/status/X-MMXXIII/Merge-Rules/resolve.yml?branch=master)

Scheduled merging of Mihomo rulesets; generates custom rule collections for personal use.

## How to Use

1. Install `python` and the required dependencies.

   ```shell
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```
2. Edit `config.yaml` to define the files you want to generate and their upstream rules as a list. The basic format is similar to Mihomo's rule-providers.

    ```
    - path: output/reject.yaml
      format: yaml
      behavior: classical
      upstream:
    
        local_reject:
          type: http
          path: "local/reject.txt"
          format: txt
          behavior: classical
    
        xndeye_reject:
          type: http
          url: "https://github.com/MetaCubeX/meta-rules-dat/raw/meta/geo/geosite/adblock.yaml"
          format: yaml
          behavior: domain
    ```
3. Run the script

   ```shell
   python rule_merger.py
   ```

## List

| 文件                   | 介绍         |          github           |            ghproxy            |            jsdelivr            |
|----------------------|:-----------|:-------------------------:|:-----------------------------:|:------------------------------:|
| `reject.yaml`        | 广告域名       |    [link][reject-raw]     |    [link][reject-ghproxy]     |    [link][reject-jsdelivr]     |
| `reject@ip.yaml`     | 广告IP       |   [link][reject@ip-raw]   |   [link][reject@ip-ghproxy]   |   [link][reject@ip-jsdelivr]   |
| `direct.yaml`        | 推荐直连域名     |    [link][direct-raw]     |    [link][direct-ghproxy]     |    [link][direct-jsdelivr]     |
| `direct@ip.yaml`     | 推荐直连IP     |   [link][direct@ip-raw]   |   [link][direct@ip-ghproxy]   |   [link][direct@ip-jsdelivr]   |
| `microsoft@cn.yaml`  | 微软中国域名     | [link][microsoft@cn-raw]  | [link][microsoft@cn-ghproxy]  | [link][microsoft@cn-jsdelivr]  |
| `apple@cn.yaml`      | 苹果中国域名     |   [link][apple@cn-raw]    |   [link][apple@cn-ghproxy]    |   [link][apple@cn-jsdelivr]    |
| `steam@cn.yaml`      | Steam 中国域名 |   [link][steam@cn-raw]    |   [link][steam@cn-ghproxy]    |   [link][steam@cn-jsdelivr]    |
| `ai.yaml`            | AI相关域名     |      [link][ai-raw]       |      [link][ai-ghproxy]       |      [link][ai-jsdelivr]       |
| `proxy.yaml`         | 推荐代理域名     |     [link][proxy-raw]     |     [link][proxy-ghproxy]     |     [link][proxy-jsdelivr]     |
| `proxy@ip.yaml`      | 推荐代理IP     |   [link][proxy@ip-raw]    |   [link][proxy@ip-ghproxy]    |   [link][proxy@ip-jsdelivr]    |
| `lan@ip.yaml`        | 局域网IP      |    [link][lan@ip-raw]     |    [link][lan@ip-ghproxy]     |    [link][lan@ip-jsdelivr]     |
| `fakeip-filter.yaml` | fakeIP过滤   | [link][fakeip-filter-raw] | [link][fakeip-filter-ghproxy] | [link][fakeip-filter-jsdelivr] |

## Complete Ruleset

Lightweight Mihomo config for personal use: [mihomo.yaml](https://github.com/X-MMXXIII/Merge-Rules/blob/master/mihomo.yaml)

> [!TIP]
> 1. Written based on the rule sets in this repository, including traffic splitting and ad-blocking, simple and ready to use.
> 2. `Fallback` means rules that do not match; this is usually kept as Direct. If certain websites cannot be accessed or if you have extra bandwidth, you can choose to follow `Select Proxy`.
> 3. Non-direct domains do not perform DNS resolution locally, so there is no so-called DNS leakage.
> 4. Please replace "Fill in your subscription address here" in the config with an existing (provider) subscription link, then import the config into your client to use.
> 5. If your client has config overrides or similar features, please adjust or disable those accordingly.

## References

- [Sukka Ruleset](https://ruleset.skk.moe)
- [Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)
- [DustinWin/domain-list-custom](https://github.com/DustinWin/domain-list-custom)
- [xndeye/adblock_list](https://github.com/xndeye/adblock_list)
- [ACL4SSR/ACL4SSR](https://github.com/ACL4SSR/ACL4SSR)

[reject-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/reject.yaml

[reject-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/reject.yaml

[reject-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/reject.yaml

[reject@ip-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/reject@ip.yaml

[reject@ip-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/reject@ip.yaml

[reject@ip-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/reject@ip.yaml

[direct-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/direct.yaml

[direct-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/direct.yaml

[direct-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/direct.yaml

[direct@ip-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/direct@ip.yaml

[direct@ip-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/direct@ip.yaml

[direct@ip-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/direct@ip.yaml

[microsoft@cn-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/microsoft@cn.yaml

[microsoft@cn-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/microsoft@cn.yaml

[microsoft@cn-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/microsoft@cn.yaml

[apple@cn-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/apple@cn.yaml

[apple@cn-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/apple@cn.yaml

[apple@cn-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/apple@cn.yaml

[steam@cn-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/steam@cn.yaml

[steam@cn-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/steam@cn.yaml

[steam@cn-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/steam@cn.yaml

[ai-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/ai.yaml

[ai-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/ai.yaml

[ai-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/ai.yaml

[proxy-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/proxy.yaml

[proxy-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/proxy.yaml

[proxy-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/proxy.yaml

[proxy@ip-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/proxy@ip.yaml

[proxy@ip-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/proxy@ip.yaml

[proxy@ip-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/proxy@ip.yaml

[lan@ip-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/lan@ip.yaml

[lan@ip-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/lan@ip.yaml

[lan@ip-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/lan@ip.yaml

[fakeip-filter-raw]: https://raw.githubusercontent.com/xndeye/rule-merger/refs/heads/release/fakeip-filter.yaml

[fakeip-filter-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/xndeye/rule-merger/release/fakeip-filter.yaml

[fakeip-filter-jsdelivr]: https://fastly.jsdelivr.net/gh/xndeye/rule-merger@release/fakeip-filter.yaml

```
