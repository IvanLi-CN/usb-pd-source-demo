# 国产支持升降压且支持 USB PD 的电源控制芯片清单（结构化）

用途：为 USB‑PD 源端/双向快充（移动电源、便携电源、桌面电源等）做初选与比对。所有候选条目均为“平级”，按同一标准入围并统一对比。量产立项前请以原厂数据手册/代理反馈为准。

## 入围标准
- 国产厂商器件，且“具备升降压能力”：
  - 集成 SoC（含升降压+PD 协议），或
  - 通过“升降压控制器 + PD 协议 IC”组合实现双向路径。
- 支持 USB PD（≥PD3.0；若支持 PD3.1/EPR/AVS 将单独标注）。
- 公开资料可核对（数据手册、权威媒体拆解或代理技术页）。
- 给出适配的电池串数与目标功率段，适合源端快充应用。
- 量产可行性：优先当前在产/可供；如为 EOL 明确标注并仅作参考。
 - 对“需协议 IC 配合”的候选，需满足下列其一：
   - 支持 FB 方案调节，或
   - 在候选条目中明确列出可配合的协议 IC 型号（已量产/已验证），并注明调压方式（FB/I2C/其他）。

## 候选列表（平级）
- 英集芯 IP2366（SoC，PD3.1/EPR，≤140W，2–6 串，集成同步升降压）
  - 参考：https://www.chongdiantou.com/archives/1752118989918.html
- 英集芯 IP2368（SoC，PD3.0，≤100W 典型，2–5 串，四管 H 桥升降压）
  - 参考：https://www.chongdiantou.com/archives/1752118989918.html
- 英集芯 IP238? 系（SoC，PD3.1/多串，家族型）
  - 参考：同系列技术汇总（含 2–6 串/140W 档）https://www.chongdiantou.com/archives/1752118989918.html
- 英集芯 IP2363（SoC，PD3.1，多串至 140W 级，集成升降压）
  - 参考：https://www.szjuquan.com/chanpin/lists_43_2.html
- 英集芯 IP2369（SoC，PD3.1，45–100W 档，2–6 串，集成升降压）
  - 参考：https://b2b.baidu.com/land?id=5085acf2a30e716fcb8259784fc4580e10
- 英集芯 IP5383（SoC，PD3.0/UFCS，≤45W，2–5 串，集成 H 桥）
  - 参考：https://www.chongdiantou.com/archives/1752118989918.html
- 英集芯 IP5385（SoC，UFCS/PD3.0，2–5 串，多口）
  - 参考：https://www.sz-dowell.com/a/solution/848.html
- 英集芯 IP5365（SoC，PD3.0，≤22.5W，1–4 串）
  - 参考：https://datasheet4u.com/datasheet/Injoinic/IP5365-1549442
- 英集芯 IP5356M（SoC，PD3.0，≈22.5W 放电，1–4 串）
  - 参考：https://m.elecfans.com/p/v106855.html
- 英集芯 IP5328P（SoC，PD3.0/PPS，18W 级，1–4 串，EOL）
  - 参考：https://item.szlcsc.com/200217.html
- 智融 SW6306（SoC，PD3.1/UFCS，≤100W，2–6 串 NMC / 2–7 串 LFP）
  - 参考：https://www.chongdiantou.com/archives/325198.html
- 智融 SW6206S（SoC，多口，PD/UFCS）
  - 参考（相关阅读链出）：https://www.chongdiantou.com/archives/325198.html
- 智融 SW6201 / SW6003（SoC，入门段，PD 多协议）
  - 参考（微信）：SW6201 https://mp.weixin.qq.com/s?__biz=MzIzNjEwOTA1MA==&mid=2650755876&idx=4#rd；SW6003 https://mp.weixin.qq.com/s?__biz=MzIzNjEwOTA1MA==&mid=2650756318&idx=4#rd
- 水芯电子 M12269/M12269H（SoC，PD3.1，≤140W 双 C 口，媒体报道）
  - 参考：https://news.qq.com/rain/a/20241010A02RD500
- 南芯 SC8815A + 南芯 SC2006A（组合，~100W，双向升降压控制器 + PD 协议）
  - 参考（拆解/报道）：https://www.chongdiantou.com/archives/1760317355369.html ｜ https://www.ednchina.com/technews/36623.html
- 南芯 SC8721 + 英集芯 IP2726/南芯 SC200x（组合，18–65W 典型，升降压控制器 + 协议）
  - 参考（拆解）：https://www.chongdiantou.com/archives/78270.html
- 南芯 SC8911（组合/全集成充电芯片，家族覆盖 20–100W，配 PD/UFCS 协议）
  - 参考（企业资讯）：https://www.vertex-icbuy.com/qiyekuaibao/7374.html
- 南芯 SC8812A（1–4 串）/ SC8902A（1–3 串）+ 协议 IC（组合，20–100W 家族）
  - 参考（企业资讯）：https://www.vertex-icbuy.com/qiyekuaibao/7374.html
- 智融 SW7201 + 协议 IC（组合，1–4 串，≤100W，双向同步升降压控制器 + 协议）
  - 参考（方案文章）：https://blog.csdn.net/zxdzwj/article/details/130993776

## 对比表（统一，平级比较）

| 类型 | 厂商 | 型号/组合 | 电池串数 | 协议/版本 | 典型/最大功率 | 关键特性 | 参考链接 |
|---|---|---|---|---|---|---|---|
| SoC | 英集芯 | IP2366 | 2–6 | PD3.1 | ≤140W | 集成同步升降压、I2C、双向快充 | https://www.chongdiantou.com/archives/1752118989918.html |
| SoC | 英集芯 | IP2368 | 2–5 | PD3.0 | ≤100W(典) | 四管 H 桥升降压，反放 | 同上 |
| SoC | 英集芯 | IP2363 | 2–6 | PD3.1 | ≤140W | 多串，家族覆盖 | https://www.szjuquan.com/chanpin/lists_43_2.html |
| SoC | 英集芯 | IP2369 | 2–6 | PD3.1 | 45–100W 档 | 多串，PD3.1 | https://b2b.baidu.com/land?id=5085acf2a30e716fcb8259784fc4580e10 |
| SoC | 英集芯 | IP5383 | 2–5 | PD3.0/UFCS | ≤45W | 集成 H 桥，多口 | https://www.chongdiantou.com/archives/1752118989918.html |
| SoC | 英集芯 | IP5385 | 2–5 | UFCS/PD3.0 | — | 多口 SoC | https://www.sz-dowell.com/a/solution/848.html |
| SoC | 英集芯 | IP5365 | 1–4 | PD3.0 | ≤22.5W | 移动电源 SoC | https://datasheet4u.com/datasheet/Injoinic/IP5365-1549442 |
| SoC | 英集芯 | IP5356M | 1–4 | PD3.0 | ≈22.5W 放电 | 双向快充 | https://m.elecfans.com/p/v106855.html |
| SoC(EOL) | 英集芯 | IP5328P | 1–4 | PD3.0/PPS | 18W 级 | 单电感升/降压+充电 | https://item.szlcsc.com/200217.html |
| SoC | 智融 | SW6306 | 2–6/2–7 | PD3.1/UFCS | ≤100W | 3.3–27.3V/10mV，I2C/库仑计 | https://www.chongdiantou.com/archives/325198.html |
| SoC | 智融 | SW6206S | — | PD/UFCS | — | 多口任意口快充 | 见上文“相关阅读” |
| SoC | 智融 | SW6201/SW6003 | 入门 | PD | — | 入门段 SoC | 微信参考链接 |
| SoC | 水芯 | M12269/H | 多串 | PD3.1 | ≤140W | 双 C 口 140W（报道） | https://news.qq.com/rain/a/20241010A02RD500 |
| 组合 | 南芯+南芯 | SC8815A+SC2006A | 多串 | PD | ~100W | 双向升降压+协议全套 | https://www.chongdiantou.com/archives/1760317355369.html |
| 组合 | 南芯+英集芯/南芯 | SC8721+IP2726/SC200x | 2.7–22V | PD | 18–65W 典 | I2C 调压/限流 | https://www.chongdiantou.com/archives/78270.html |
| 组合 | 南芯+(协议) | SC8911(+协议) | 家族 | PD/UFCS | 20–100W | 全集成双向升降压 | https://www.vertex-icbuy.com/qiyekuaibao/7374.html |
| 组合 | 南芯+(协议) | SC8812A/SC8902A(+协议) | 1–4/1–3 | PD | 20–100W | 双向升降压控制器 | https://www.vertex-icbuy.com/qiyekuaibao/7374.html |
| 组合 | 智融+(协议) | SW7201(+协议) | 1–4 | PD | ≤100W | 双向同步升降压控制器 | https://blog.csdn.net/zxdzwj/article/details/130993776 |

注：表中“(典)”为典型设计功率；“组合”类需搭配相应 PD 协议 IC 才能实现完整源端 PD 功能。
