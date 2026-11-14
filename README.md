# Gemini 原生 IP VPS 怎么选：Akile 哪一档够跑、一个月多少钱、买错能不能退？（附全套餐价格表与 IP 自测三步）

想给 Gemini 找一个干净的出口，Akile 这边最省钱的一档是日本 JPHyper-Lite：¥14.99/月，1 核、1.5G 内存、10G 硬盘、1TB 月流量、2.5Gbps 端口。一个人跑 API 反代，顺手挂个 Cherry Studio 或 n8n，这个配置够用。要几个人共用，或者同一台机器上还要跑面板和数据库，香港 HKLite-Pre-Mini 更合适：2 核 4G、30G 硬盘、2.5TB 流量、5Gbps，¥39.99/月。

有件事得先讲清楚。Akile 没有公开承诺过哪一档能解锁 Gemini，原生 IP 只说明这台机器真的在日本或美国，不等于 Google 认它。所以下面除了套餐和价格，还会讲原生 IP 怎么自己验、买回来先做哪三件事、哪些档位看着便宜其实用不上，以及退款和换 IP 这两件下单前必须确认的事。

> **选购速览**
>
> - 一个人跑 Gemini API 反代：日本 JPHyper-Lite，¥14.99/月，1TB 月流量对纯文本调用很宽裕
> - 团队共用、多个下游工具：香港 HKLite-Pre-Mini，¥39.99/月，2 核 4G 起步
> - 要多开几个独立 IP 做隔离：洛杉矶 LAXLite-One，¥8.88/月起，开三台比堆一台高配便宜
>
> 👉 [打开 Akile 注册入口，先开一台日本入门档试水](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811)

## Akile 现在在卖的套餐和价格

Akile 的档位按地区分系列：日本有 JPHyper 和 JPPro，香港是 HKLite，洛杉矶是 LAXLite 和 LAXPro，新加坡是 SGLite，全部人民币计价、按月付费。同一档在不同渠道的标注偶尔有出入，比如 JPHyper-Lite 的内存有写 1.5G 的也有写 2G 的，下单页显示的那份才算数。

| 地区 | 套餐 | 配置（CPU / 内存 / 硬盘） | 流量 / 带宽 | 月付 | 购买 |
| --- | --- | --- | --- | --- | --- |
| 日本 | JPHyper-Lite | 1 核 / 1.5G / 10G SSD | 1TB / 2.5Gbps | ¥14.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 日本 | JPHyper-Mini | 2 核 / 2G / 10G SSD | 2.5TB / 2.5Gbps | ¥25.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 日本 | JPHyper-Starter | 2 核 / 2G / 10G SSD | 5TB / 2.5Gbps | ¥49.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 日本 | JPHyper-Standard | 2 核 / 2G / 20G SSD | 10TB / 2.5Gbps | ¥99.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 日本 | JPHyper-Pro | 2 核 / 4G / 20G SSD | 30TB / 2.5Gbps | ¥289.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 日本 | JPPro-Light | 1 核 / 1G / 10G SSD | 700GB / 300Mbps | ¥24.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 日本 | JPPro-Starter | 1 核 / 1G / 20G SSD | 500GB / 1Gbps | ¥37.35 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 日本 | JPPro-Standard | 1 核 / 1G / 20G SSD | 1TB / 1.2Gbps | ¥62.25 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 香港 | HKLite-Mini | 1 核 / 1G / 10G SSD | 2.5TB / 1Gbps | ¥24.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 香港 | HKLite-Pre-Mini | 2 核 / 4G / 30G SSD | 2.5TB / 5Gbps | ¥39.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 香港 | HKLite-Starter | 1 核 / 1G / 10G SSD | 5TB / 1Gbps | ¥43.74 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 香港 | HKLite-Standard | 2 核 / 1G / 20G SSD | 10TB / 2Gbps | ¥99.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 香港 | HKLite-Pro | 2 核 / 2G / 20G SSD | 30TB / 2Gbps | ¥237.49 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 洛杉矶 | LAXLite-One | 1 核 / 1G / 5G SSD | 1TB / 5Gbps | ¥8.88 起 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 洛杉矶 | LAXLite-Mini | 1 核 / 2G / 10G SSD | 2TB / 5Gbps | ¥15.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 洛杉矶 | LAXLite-Starter | 2 核 / 2G / 10G SSD | 5TB / 5Gbps | ¥34.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 洛杉矶 | LAXPro-Light | 1 核 / 1G / 20G SSD | 300GB / 300Mbps | ¥43.74 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 洛杉矶 | LAXPro-Standard | 1 核 / 1G / 20G SSD | 1TB / 500Mbps | ¥74.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 新加坡 | SGLite-One | 1 核 / 1G / 5G SSD | 1TB / 500Mbps | ¥10.42 起 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 新加坡 | SGLite-Mini | 1 核 / 1G / 5G SSD | 1TB / 1Gbps | ¥24.99 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 新加坡 | SGLite-Starter | 1 核 / 1G / 10G SSD | 3TB / 1Gbps | ¥43.74 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |
| 新加坡 | SGLite-Standard | 1 核 / 1G / 10G SSD | 6TB / 1.5Gbps | ¥87.49 | [开通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811) |

日本另有一组 JPBase 档和按独享带宽计费的型号，上架时间更早，价格和是否仍在售要进下单页确认：

| 套餐 | 配置（CPU / 内存 / 硬盘） | 流量 / 带宽 | 月付 |
| --- | --- | --- | --- |
| JPBase-Mini | 1 核 / 512M / 5G | 1500G / 1Gbps | ¥19.99 |
| JPBase-Lite | 1 核 / 1G / 10G | 3T / 2Gbps | ¥35 |
| JPBase-Standard | 1 核 / 2G / 10G | 6T / 2Gbps | ¥70 |
| JPBase-UNLIMITED-500M | 1 核 / 2G / 10G | 不限 / 500Mbps | ¥235 |
| JPBase-UNLIMITED-1000M | 1 核 / 3G / 20G | 不限 / 1Gbps | ¥360 |
| JPHyper-300M 独享 | 4 核 / 4G / 20G | 不限 / 300Mbps | ¥599.99 |
| JPHyper-500M 独享 | 4 核 / 8G / 30G | 不限 / 500Mbps | ¥999.99 |
| JPHyper-1000M 独享 | 8 核 / 16G / 50G | 不限 / 1Gbps | ¥1899.99 |

### 价格表里三个容易被忽略的地方

**年付没有折扣。** 以 LAXLite-One 为例，标价 ¥8.88/月起，年付 ¥106.56，正好是 8.88 乘 12。年付换来的是省事，不用每个月续，不是省钱。第一次买建议月付，跑满一个周期确认 IP 稳定再考虑长周期。

**Pro 系列不一定比 Lite/Hyper 强。** JPPro-Light 卖 ¥24.99，配置是 1 核 1G、700GB 流量、300Mbps；JPHyper-Lite 卖 ¥14.99，是 1 核 1.5G、1TB 流量、2.5Gbps。贵十块钱，配置反而低一档。日本系列的套餐说明提到「包含直连和路由调优型号」，但没写明哪个型号走哪种路由，所以这十块钱买到的是什么，下单前你得自己在页面线路说明里找。洛杉矶的 LAXPro 也是同样情况，官方资料没说它和 LAXLite 在网络上有何区别。

**端口速率和月流量是两件事。** 2.5Gbps 指的是峰值能跑多快，1TB 是这个月累计能传多少。峰值高不代表流量多，跑 API 看的是流量，别被 Gbps 的数字带跑。

## 原生 IP 到底是什么，Gemini 为什么在意

原生 IP 要求四件事对得上：IP 的注册国家、宣告这个 IP 的本地网络、地理定位数据库显示的国家、服务器真实所在地，全在同一国。对照的是广播或借用 IP，在一地宣告、注册或标注成另一地，不同地理库可能给出不同国家，数据库一更新结论还会变。

想自己验，四步就够了：

1. 跑 `whois 你的IP`，看 `country` 字段和网络所有者。日本、韩国属于 APNIC 管区，注册信息应该落在对应国家。
2. 拿两三个公开地理定位库交叉比对国家和城市，原生 IP 在几个库里显示的国家应该一致。
3. 查 ASN，看宣告这个 IP 的自治系统是不是当地运营的网络。
4. 新分配的 IP 可能还显示旧数据，数据库刷新周期不同，给它几天时间。

厂商自己也把话说得很明确：原生 IP 只描述服务器真实所在地，不保证任何第三方服务可用，也不是绕过别人服务条款或地区规则的办法。这句话值得记住，它是所有「原生 IP 解锁」宣传的天花板。

Gemini 盯 IP，是因为它按 IP 归属国判断能不能用、要不要限流。被反复滥用的数据中心段、进过风控名单的 IPv6 段，轻则限流，重则把 API key 一起封掉。很多人还要把 Gemini 反代成 OpenAI 兼容接口喂给 Cherry Studio、LobeChat、n8n，出口 IP 干不干净直接决定整条链路能不能跑。有个开源项目的做法很能说明问题：机房分配的 IPv6 段在 Google 的 IP 库里经常被定位错误、信誉偏低，登录 gemini.google.com 直接被挡，它的解法是用 Xray 加 Cloudflare WARP 链式出站，绕到干净的美国出口。

放到 Akile 身上：日本系列官方说明里提到机房支持当地流媒体解锁，美国有 4837 原生 IP 的档位，但官方没有对 Gemini 单独出过承诺。第三方对一台 Akile 香港不限流量机的实测里，ChatGPT 和 Gemini 都显示不可用。同一家商家，不同 IP 段的结果可以完全相反，这正是「买前确认条款、买后立刻自测」的理由。

👉 [从 Akile 注册入口进去，下单前先把退款条款和线路说明翻一遍](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811)

## 买回来先做的三件事

别急着装环境，先花二十分钟把这台机器的底细摸清楚，这几步要放在退款窗口内做完。

**第一件，whois 看归属。** `whois 你的IP`，`country` 是 JP 还是 US，网络所有者是不是当地运营商，ASN 是多少。显示的国家和套餐标的地不一致，直接找客服，别自己折腾。

**第二件，ipinfo.io 看 ASN 类型。** 页面上会标这个 ASN 属于 Hosting Provider / Data Center 还是 ISP。机房段就是机房段，标注成住宅的才可能是真住宅。顺手看一眼 abuseipdb 上的历史滥用报告次数，一条没有最好，十几条就别用来跑重要业务。

**第三件，scamalytics 看风险分。** 0 到 25 分算干净，50 分以上基本别指望稳定。再拿 Spamhaus 查一下有没有进黑名单。这两项都过关，再登录 gemini.google.com 用这台机器的网络实测一次，然后把你的 API 调用完整跑一遍，别只测首页能不能打开。

还有个使用习惯上的事：一个应用、一个账号、一个 IP。同一台机器上挂三四个 Gemini key 轮询，或者几个账号共用同一个出口，一个触发风控，其他跟着连坐。真要隔离，开三台 LAXLite-One 比把一台机器堆到 8 核有用得多，价格还更低。

## 按场景选档：四种用法，四种配置

**一个人跑 Gemini API 反代。** 并发就你一个，内存 1G 出头够，硬盘 5G 够装系统和反代程序。JPHyper-Lite ¥14.99 是这套需求的下限，再往下省的几块钱会省掉内存和流量。跑通了、觉得稳，再考虑要不要加到 JPHyper-Mini。

**团队共用，或者一台机器上跑多个下游。** Cherry Studio、LobeChat、n8n 各占一个容器，再加上反代和监控，1G 内存会紧张。JPHyper-Mini ¥25.99（2 核 2G、2.5TB）是这一档的起点，人多或者要跑数据库就上 HKLite-Pre-Mini ¥39.99，2 核 4G、30G 硬盘、5Gbps 端口，香港机房离国内近，管理面板反应快。

**多账号需要 IP 隔离。** 关键在 IP 数量，不在单机性能。开三台 LAXLite-One，¥8.88 乘 3，一个月二十六块出头，拿到三个独立 IP，比一台高配机器挤一个出口安全。Akile 单机默认给一个 IP，要更多 IP 只能多开实例或者看有没有加购选项。

**大流量长期跑。** 先算清楚一个月要传多少。纯文本 API 调用很难跑满 1TB，真跑到几 TB 的通常是文件、图片、音视频中转。按流量选档更直接：5TB 看 HKLite-Starter ¥43.74，10TB 看 HKLite-Standard ¥99.99，30TB 才轮到 HKLite-Pro ¥237.49。别为了「以后可能用得上」提前买大档，流量月底清零，用不完不退。

## 哪些档位不建议买，哪些人不适合 Akile

**不建议买的：**

- **JPPro 和 LAXPro 全系。** 不是配置不够，是同价位有更好的选择。JPPro-Light ¥24.99 给 700GB 流量和 300Mbps，JPHyper-Lite ¥14.99 给 1TB 和 2.5Gbps。除非下单页明确写了 Pro 走的是另一条优化线路，否则这钱花得没道理。
- **共享 NAT 的低价档。** 台湾、越南那些月付十几块的入门型号用的是 NAT 的 IPv4，一个公网 IP 后面挂多个用户。Gemini 这类服务看到一个出口上跑着几十个不相干的行为，风控只会更严。省钱省在这里，等于把预算花在了一个注定要换掉的东西上。
- **超低带宽的存储型。** 端口只有 0.03Gbps（约 30Mbps）而硬盘给到 80G、100G 的那些香港档，定位是大存储，跑 API 中转不是它的用途。

**不适合 Akile 的情况：**

想要厂商白纸黑字保证 Gemini 长期可用的，这里没有这个承诺，同类商家也都没有。需要一台机器上挂多个独立 IPv4 的，Akile 的标准套餐给不了，得上多开或者换独立服务器方案。要做对外生产环境的 API 网关、不能接受中途换 IP 的，先把换 IP 的成本和流程问清楚再决定。

退款和换 IP 这两项，Akile 目前没有公开写明的统一政策。同类商家的做法差异很大，有的 48 小时内无条件退，有的给 3 天，有的明确写「不免费换 IP，要换自己加购」。这三件事必须在下单前从 Akile 的条款页或工单里问出来：几天内能退、退款扣不扣手续费、IP 被墙或被风控能不能免费换。

👉 [进 Akile 注册页看当前档位，顺手把退款和换 IP 的条款找出来](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811)

## 同类商家价格参照

不看链接，只比标价，判断 Akile 这个价位在市场里处在什么位置。

| 商家 | 地区 | 入门价 | 计费 | 已知信息 |
| --- | --- | --- | --- | --- |
| Akile | 日本 | ¥14.99/月 | 月付 | 1 核 1.5G、1TB、2.5Gbps |
| Akile | 洛杉矶 | ¥8.88/月起 | 月付 / 年付 | 1 核 1G、1TB、5Gbps |
| JUSTG | 东京 / 首尔 | $19.99/月，$119.99/年 | 月付 / 年付 | 含 1 个原生 IPv4 + 免费 IPv6、500Mbps；官方称 2026 年 10 月测试中 ChatGPT、Claude、Gemini、Netflix、Disney+ 五项通过 |
| LisaHost | 法兰克福 | ¥68/月 | 月付 / 年付 | 1 核 1G、10G NVMe、3000GB、100Mbps，双栈双原生 IP，48 小时内不满意无条件退款 |
| 野草云 | 香港 | ¥118/年 | 年付为主 | 1 核 1G、10G NVMe、500GB、200Mbps，3 天内可退款 |
| 六六云 | 美国 | ¥45/月起 | 月付 | 原生 IP、AS4837 回程，48 小时退款 |

价差摆在这里：Akile 的日本入门档 ¥14.99/月，JUSTG 的东京同级别是 $19.99/月，LisaHost 的德国档 ¥68/月。贵出来的部分买的是明确的解锁测试口径、退款承诺和更细的线路说明。你要的是最低成本先把 Gemini 跑通，Akile 这类便宜档值得试；你要的是一年内不想再折腾，多花的钱买的是确定性。

## FAQ

**原生 IP 就一定能用 Gemini 吗？**

不一定。原生 IP 解决的是「IP 归属地真实」这一个问题，Gemini 还看这个 IP 段的历史行为、同段其他用户干过什么、以及 Google 自己的风控名单。原生 IP 是入场券，不是通行证。

**月付还是年付划算？**

按目前标价，年付基本等于月付乘 12，没有额外折扣。先月付跑一个月，确认 IP 没被风控、延迟能接受，再决定要不要锁长周期。

**Gemini 突然不能用了怎么办？**

先确认是不是 IP 的问题：换一台机器登录同一账号，能通就是 IP 的事。是 IP 的话有三条路，提交工单让商家核查、加购一个新 IP、或者直接销毁旧实例重建一台（先开新机确认新 IP 和旧 IP 不同，再删旧的，避免被分回同一个地址）。哪种可行取决于 Akile 的实际政策，下单前就该问清楚。

**2.5Gbps 端口配 1TB 流量是不是浪费？**

不浪费，两个指标各管各的。端口决定单次传输能跑多快，流量决定这个月总共能传多少。峰值高、总量小的组合适合突发型业务，比如偶尔拉个大文件。

**香港和日本选哪个？**

只看 Gemini，两地都能跑，选便宜的那档。要顺带看日区流媒体，日本机房官方说明里提到了当地流媒体支持。管理面板要天天开、对操作响应敏感，香港机型体验更好。

## 最后：三条决策规则

- 只是想用最低成本把 Gemini 跑通，一个人用 → 日本 JPHyper-Lite，¥14.99/月，跑满一个月再说
- 两三个人共用，或者机器上还要跑面板、数据库、自动化工具 → 香港 HKLite-Pre-Mini，¥39.99/月
- 要多个独立 IP 做账号隔离 → 开多台 LAXLite-One，每台 ¥8.88 起，IP 数量比单机性能重要

下单前最后确认三件事：退款窗口是几天、续费价和首单价是否一致、套餐给的是独立 IPv4 还是共享 NAT。这三条问清楚了，剩下的就是买回来做自测。

👉 [从 Akile 注册页开始，先开一台 ¥14.99/月的日本入门档验证 Gemini 能不能通](https://akile.io/register?aff_code=24a6f6bd-f995-4158-a9fd-f4b6aef27811)
