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
    - path: output/mrs/ai.mrs
      format: mrs
      behavior: domain

      upstream:
        skk_ai:
          type: http
          url: "https://ruleset.skk.moe/Clash/non_ip/ai.txt"
          format: text
          behavior: classical

        DustinWin_ai:
          type: http
          url: "https://github.com/DustinWin/domain-list-custom/releases/download/domains/ai.list"
          format: text
          behavior: classical

        ACL4SSR_ai:
          type: http
          url: "https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/refs/heads/master/Clash/Ruleset/AI.list"
          format: text
          behavior: classical

        MetaCubeX_ai-!cn:
          type: http
          url: "https://github.com/MetaCubeX/meta-rules-dat/raw/meta/geo/geosite/category-ai-!cn.yaml"
          format: yaml
          behavior: domain

        local_ai:
          type: file
          path: local/ai.yaml
          format: yaml
          behavior: classical
    ```
3. Run the script

   ```shell
   python rule_merger.py
   ```

## List Notes

| 文件名                         | 介绍                                       |
|:-----------------------------:|-------------------------------------------|
| `*.yaml` `*.mrs`              | 域名类规则                                  |
| `*_ip.yaml` `*_ip.mrs`        | IP类规则                                   |
| `*@cn.yaml` `*@cn.mrs`        | 有中国接入点的域名类规则                      |
| `cdn.yaml` `cdn.mrs`          | 常用对象存储和静态资源CDN域名                  |
| `cn.yaml` `cn.mrs`            | 中国大陆可用的已知地址                        |
| `cn_ip.yaml` `cn_ip.mrs`      | 中国大陆广播的所有`IPv4` `IPv6`地址段          |
| `global.yaml` `global.mrs`    | `GFW` + `!CN` 及一些在中国大陆不可用的服务域名  |


## Complete Ruleset

Lightweight Mihomo config for personal use: [mihomo.yaml](https://github.com/X-MMXXIII/Merge-Rules/raw/master/mihomo.yaml)

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

[reject-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/reject.yaml

[reject-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/reject.yaml

[reject-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/reject.yaml

[reject@ip-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/reject@ip.yaml

[reject@ip-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/reject@ip.yaml

[reject@ip-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/reject@ip.yaml

[direct-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/direct.yaml

[direct-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/direct.yaml

[direct-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/direct.yaml

[direct@ip-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/direct@ip.yaml

[direct@ip-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/direct@ip.yaml

[direct@ip-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/direct@ip.yaml

[microsoft@cn-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/microsoft@cn.yaml

[microsoft@cn-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/microsoft@cn.yaml

[microsoft@cn-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/microsoft@cn.yaml

[apple@cn-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/apple@cn.yaml

[apple@cn-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/apple@cn.yaml

[apple@cn-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/apple@cn.yaml

[steam@cn-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/steam@cn.yaml

[steam@cn-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/steam@cn.yaml

[steam@cn-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/steam@cn.yaml

[ai-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/ai.yaml

[ai-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/ai.yaml

[ai-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/ai.yaml

[proxy-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/proxy.yaml

[proxy-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/proxy.yaml

[proxy-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/proxy.yaml

[proxy@ip-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/proxy@ip.yaml

[proxy@ip-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/proxy@ip.yaml

[proxy@ip-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/proxy@ip.yaml

[lan@ip-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/lan@ip.yaml

[lan@ip-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/lan@ip.yaml

[lan@ip-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/lan@ip.yaml

[fakeip-filter-raw]: https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/refs/heads/release/fakeip-filter.yaml

[fakeip-filter-ghproxy]: https://ghproxy.net/https://raw.githubusercontent.com/X-MMXXIII/Merge-Rules/release/fakeip-filter.yaml

[fakeip-filter-jsdelivr]: https://fastly.jsdelivr.net/gh/X-MMXXIII/Merge-Rules@release/fakeip-filter.yaml

