# 国产支持升降压且支持 USB PD 的电源控制芯片候选清单

用途：为 USB-PD 源端/双向快充设计（移动电源、便携电源、桌面电源等）做初选对照。信息基于公开资料核对，量产立项前建议与原厂/代理确认供货状态与最新规格。

## 一体化 SoC（集成 PD 协议 + 升降压）

- Injoinic 英集芯 IP2366（PD3.1，双向，最高 140W）
  - 要点：集成同步升降压；支持多串（最多 6 串）锂/铁锂；I2C；电量显示接口。
  - 参考：充电头网专题 https://www.chongdiantou.com/archives/1752118989918.html

- Injoinic 英集芯 IP2368（PD3.0，双向，至 100W 级）
  - 要点：内置四管 H 桥同步升降压；支持 2–5 串；支持反向放电至 100W（典型方案）。
  - 参考：充电头网专题 https://www.chongdiantou.com/archives/1752118989918.html

- Injoinic 英集芯 IP5383（PD3.0/UFCS，2–5 串，至 45W）
  - 要点：集成 H 桥功率 MOS；适合中功率多串移动电源。
  - 参考：充电头网条目（含参数概述） https://www.chongdiantou.com/archives/1752118989918.html

- Injoinic 英集芯 IP5365（PD3.0 SoC，22.5W 档）
  - 要点：移动电源 SoC，集成升降压与充电管理；多口应用常见。
  - 参考：Datasheet4U 产品页 https://datasheet4u.com/datasheet/Injoinic/IP5365-1549442

- Injoinic 英集芯 IP5356M（双向 PD3.0，多协议 SoC）
  - 要点：集成升降压；22.5W 放电/18W 充电级别；多协议兼容。
  - 参考：电子发烧友介绍 https://m.elecfans.com/p/v106855.html

- Injoinic 英集芯 IP5328P（PD3.0/PPS SoC，1–4 串，约 18W；注意停产）
  - 要点：老牌移动电源 SoC，单电感实现升/降压与充电管理；带 PD/PPS。
  - 参考：立创商城（标注停产与规格）https://item.szlcsc.com/200217.html

- 智融科技 SW6306（PD3.1/UFCS，双向同步升降压，最高 100W）
  - 要点：2–6 串三元或 2–7 串铁锂；输入 4–26V、输出 3.3–27.3V，10mV 步进；I2C、库仑计；多口 A+A+C+C 方案。
  - 参考：充电头网评测 https://www.chongdiantou.com/archives/325198.html

## 组合方案（升降压控制器 + PD 协议芯片）

- Southchip 南芯 SC8815A（双向同步升降压）+ 南芯 SC2006A（PD 协议）
  - 要点：被 100W 级移动电源采用的全套方案，支持多串电池与双向快充。
  - 参考：
    - 充电头网视频拆解（华为 100W 全能充，SC8815A+SC2006A）https://www.chongdiantou.com/archives/1760317355369.html
    - EDN China 拆解报道（同款产品用料与方案）https://www.ednchina.com/technews/36623.html

- Southchip 南芯 SC8721（同步升降压控制器）+ 英集芯 IP2726 或 南芯 SC200x（PD 协议）
  - 要点：2.7–22V 输入/输出，支持 I2C 调压与限流；常与 PD 协议 IC 搭配做多口快充。
  - 参考：充电头网（联想 YOGA 相关产品采用 SC8721 + IP2726）https://www.chongdiantou.com/archives/78270.html

---

选型提示
- >100W 或 PD3.1（AVS/EPR）优先：英集芯 IP2366、智融 SW6306。
- 中功率多串（≤45–100W）：英集芯 IP2368/IP5383、南芯 SC8815A 组合。
- 入门/单串移动电源：英集芯 IP5365/IP5356M（注意 IP5328P 已停产）。
- 多口与协议覆盖（含 PPS/UFCS）：智融 SW6306、英集芯 IP538x/5365。

注：以上为初筛清单，实际设计需结合目标功率、串数、端口数量/分配、是否需 PPS/AVS、效率与热设计裕量、BOM 与供货周期综合评估。

## 对照表（初版）

### SoC（集成 PD 协议 + 升降压）

| 厂商 | 型号 | 电池串数 | 协议/版本 | 典型功率 | 关键特性 | 资料链接 |
|---|---|---|---|---|---|---|
| Injoinic 英集芯 | IP2366 | 2–6 串 | PD3.1（EPR/AVS）等 | ≤140W | 集成同步升降压、I2C、电量显示，双向快充 | https://www.chongdiantou.com/archives/1752118989918.html |
| Injoinic 英集芯 | IP2368 | 2–5 串 | PD3.0 等 | ≤100W（典型方案） | 内置四管 H 桥升降压，支持反向放电 | https://www.chongdiantou.com/archives/1752118989918.html |
| Injoinic 英集芯 | IP5383 | 2–5 串 | PD3.0/UFCS | ≤45W | 集成 H 桥功率 MOS，多口移动电源 | https://www.chongdiantou.com/archives/1752118989918.html |
| Injoinic 英集芯 | IP5365 | 1–4 串 | PD3.0 等 | ≤22.5W | 移动电源 SoC，集成升降压/充电管理 | https://datasheet4u.com/datasheet/Injoinic/IP5365-1549442 |
| Injoinic 英集芯 | IP5356M | 1–4 串 | PD3.0 等 | 放电≈22.5W | 集成升降压，双向快充 | https://m.elecfans.com/p/v106855.html |
| Injoinic 英集芯 | IP5328P（EOL） | 1–4 串 | PD3.0/PPS 等 | 18W 级 | 单电感升/降压+充电管理 | https://item.szlcsc.com/200217.html |
| 智融科技 | SW6306 | 2–6 串（NMC）/ 2–7 串（LFP） | PD3.1/UFCS 等 | ≤100W | 双向同步升降压，3.3–27.3V/10mV 步进，I2C、库仑计，多口 | https://www.chongdiantou.com/archives/325198.html |
| 智融科技 | SW6206S | 多口 | PD/UFCS | — | 多口任意口快充 SoC | 见“相关阅读”链出：https://www.chongdiantou.com/archives/325198.html |
| 智融科技 | SW6201 / SW6003 | 入门段 | PD 等 | — | 入门功率段双向快充 SoC | SW6201：https://mp.weixin.qq.com/s?__biz=MzIzNjEwOTA1MA==&mid=2650755876&idx=4&sn=67396e73a4fd6800aa07547dfae69b86&chksm=f0d71eb1c7a097a78161a9ebde57391a5cc28a71d5c8621702559cbaabedfcebdedd4cb177da#rd；SW6003：https://mp.weixin.qq.com/s?__biz=MzIzNjEwOTA1MA==&mid=2650756318&idx=4&sn=613d559e709bcdc96277c9b576b3cf1d&chksm=f0d7194bc7a0905d3fce71731fcf2dd22e76f8f94ab036c184f0fcfb91a755088ecaf0cdac85#rd |
| 水芯电子 | M12269 / M12269H | 多串 | PD3.1 | ≤140W（双 C 口） | 多口双向快充 SoC（媒体报道） | https://news.qq.com/rain/a/20241010A02RD500 |

### 组合（升降压控制器 + PD 协议芯片）

| 控制器 | 协议 IC | 应用功率 | 关键特性 | 资料链接 |
|---|---|---|---|---|
| Southchip 南芯 SC8815A | 南芯 SC2006A（PD） | ~100W 级 | 双向同步升降压 + 协议全套，品牌移动电源量产案例 | 拆解（华为 100W 全能充）：https://www.chongdiantou.com/archives/1760317355369.html；EDN 报道：https://www.ednchina.com/technews/36623.html |
| Southchip 南芯 SC8721 | 英集芯 IP2726/南芯 SC200x | 18–65W 典型 | 同步升降压 2.7–22V，I2C 调压/限流，常见多口方案 | 联想相关拆解：https://www.chongdiantou.com/archives/78270.html |
| Southchip 南芯 SC8911 | （配 PD/UFCS 协议） | 20–100W（家族覆盖） | 全集成双向升降压充电芯片（官方资讯） | https://www.vertex-icbuy.com/qiyekuaibao/7374.html |
| Southchip 南芯 SC8812A（1–4 串）/ SC8902A（1–3 串） | SC2006A/IP2726 等 | 20–100W（家族覆盖） | 双向升降压控制器，配协议 IC 组网 | https://www.vertex-icbuy.com/qiyekuaibao/7374.html |

## 更多候选（增补）

### 一体化 SoC（集成 PD 协议 + 升降压）

- Injoinic 英集芯 IP2363（PD3.1，多串，至 140W 级）
  - 要点：2–6 串锂/铁锂充放电管理，集成同步升降压与快充协议。
  - 参考：代理技术页（含 PD3.1 与 2–6 串说明）https://www.szjuquan.com/chanpin/lists_43_2.html

- Injoinic 英集芯 IP2369（PD3.1，45–100W 档位，支持 2–6 串）
  - 要点：多串移动电源 SoC，集成升降压与快充协议。
  - 参考：B2B 资料页（规格与功率档）https://b2b.baidu.com/land?id=5085acf2a30e716fcb8259784fc4580e10

- Injoinic 英集芯 IP5385（UFCS/PD3.0 SoC，2–5 串，多口应用）
  - 要点：集成 H 桥升降压功率管与多协议，适合 2–5 串多口移动电源。
  - 参考：
    - 技术方案页 https://www.sz-dowell.com/a/solution/848.html
    - 媒体报道（小米澎湃闪充首发案例文）https://post.smzdm.com/p/a2403l6q/

- 智融科技 SW6206S（多口移动电源 SoC，PD/UFCS 多协议）
  - 要点：面向移动电源主控的 SoC，支持多口任意口快充。
  - 参考：充电头网「相关阅读」链出微信文章（获绿联采用）
    - https://mp.weixin.qq.com/s?__biz=MzIzNjEwOTA1MA==&mid=2650735187&idx=5&sn=566f8d5dd39e4eba1c341bd516bede39&chksm=f0d74fc6c7a0c6d020336fb1d8726a25266dac9a67cc75c83fa33068f9748fd11524b1ccda8b&scene=178&cur_album_id=1599555034046889986#rd

- 智融科技 SW6201 / SW6003（入门功率段移动电源 SoC，含 PD 多协议）
  - 要点：适合 20–30W 等入门段移动电源的 SoC（双向快充、集成升降压）。
  - 参考（充电头网「相关阅读」链出微信文章）：
    - SW6201：https://mp.weixin.qq.com/s?__biz=MzIzNjEwOTA1MA==&mid=2650755876&idx=4&sn=67396e73a4fd6800aa07547dfae69b86&chksm=f0d71eb1c7a097a78161a9ebde57391a5cc28a71d5c8621702559cbaabedfcebdedd4cb177da&scene=178&cur_album_id=1599555034046889986#rd
    - SW6003：https://mp.weixin.qq.com/s?__biz=MzIzNjEwOTA1MA==&mid=2650756318&idx=4&sn=613d559e709bcdc96277c9b576b3cf1d&chksm=f0d7194bc7a0905d3fce71731fcf2dd22e76f8f94ab036c184f0fcfb91a755088ecaf0cdac85&scene=178&cur_album_id=1599555034046889986#rd

- 水芯电子 M12269/M12269H（PD3.1，140W 多口双向快充 SoC）
  - 要点：面向多串与大功率，双 C 口 140W 双向快充方案报道。
  - 参考：腾讯新闻行业稿（含产品采用案例）https://news.qq.com/rain/a/20241010A02RD500

### 组合方案（升降压控制器 + PD 协议芯片）

- Southchip 南芯 SC8911（全集成双向升降压充电芯片）
  - 要点：官方资讯指向支持 PD/UFCS 等协议生态，面向多模式切换与精细调压。
  - 参考：企业资讯稿（并提及 SC8902A/SC8812A 系列覆盖 20–100W）https://www.vertex-icbuy.com/qiyekuaibao/7374.html

- Southchip 南芯 SC8812A（1–4 串双向升降压控制器）/ SC8902A（1–3 串）+ 协议芯片（SC2006A/IP2726 等）
  - 要点：多串双向升降压控制器，常与 PD 协议 IC 组合用于 20–100W 档移动电源。
  - 参考：企业资讯稿 https://www.vertex-icbuy.com/qiyekuaibao/7374.html
