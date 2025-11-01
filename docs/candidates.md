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

## 候选列表

本章节对每一款“候选”单独建节，统一包含：介绍、特性、适用场景、性能指标、案例（若有）。

### 英集芯 IP2366（SoC）

- 介绍：多串锂/铁锂充放电管理 SoC，集成同步升降压与 PD3.1/EPR 协议，支持双向快充，适合 ≥100W 级移动/便携电源。
- 特性：2–6 串电池；集成升降压；支持 PD2.0/PD3.0/PD3.1 等；I2C、电量显示接口；高集成单电感方案。
- 适用场景：笔电级移动电源、便携储能子系统、多口桌面电源的电池侧。
- 性能指标：最大功率至 140W（公开资料）；多协议输入/输出；典型单电感。
- 参考链接：充电头网专题 https://www.chongdiantou.com/archives/1752118989918.html

### 英集芯 IP2368（SoC）

- 介绍：集成同步升降压驱动的充电管理 SoC，支持 PD3.0，定位 2–6 串、百瓦内充电应用。
- 特性：集成 BUCK-BOOST 驱动；2–6 串；支持 PD3.0、AFC/FCP 等；I2C；LED 电量指示/NTC；多重保护。
- 适用场景：多串电池充电底板、移动电源电池侧充电管理、工具电池座 PD 自充。
- 性能指标：最大充电功率 100W；单节满充电压 4.1–4.4V 可设（亦支持 LFP 对应电压）；封装 QFN48 7×7mm。
- 参考链接：数据手册（ChipSourceTek 托管）https://www.chipsourcetek.com/DataSheet/IP2368_v1.35.pdf

### 英集芯 IP2363（SoC）

- 介绍：IP236x 家族款，定位 PD3.1 多串高功率场景，覆盖至 140W 档。
- 特性：多串、集成升降压、PD3.1；家族规格与 IP2366 类似。
- 适用场景：大功率移动电源/多串电池充放电管理。
- 性能指标：多串（2–6）；百瓦级功率段。
- 参考链接：代理技术页 https://www.szjuquan.com/chanpin/lists_43_2.html

### 英集芯 IP2369（SoC）

- 介绍：PD3.1 多串充放电 SoC，覆盖 45–100W 档位，适合 2–6 串。
- 特性：多协议输入；集成升降压；I2C 管理。
- 适用场景：中高功率移动电源、双向快充扩展板。
- 性能指标：充电 100W、放电可达 140W（渠道页综合信息，需以原厂规格为准）。
- 参考链接：B2B 规格页 https://b2b.baidu.com/land?id=5085acf2a30e716fcb8259784fc4580e10

### 英集芯 IP5383（SoC）

- 介绍：移动电源 SoC，集成双向同步升降压、锂电充管、PD3.0/UFCS 等多协议，适合 2–5 串中功率移动电源。
- 特性：QC2.0/QC3.0/SCP/UFCS 输出；AFC/FCP 输入/输出；PD2.0/PD3.0 输入/输出；PD3.0 PPS 输出；BC1.2/Apple；集成双向升降压与电量指示。
- 适用场景：2–5 串移动电源、桌面多口电源内置电池版。
- 性能指标：45W 档典型（家族档位）；集成 H 桥；SoC 单芯片方案。
- 参考链接：Datasheet4U https://datasheet4u.com/datasheet/Injoinic/IP5383-1549436 ，Dowell PDF http://www.sz-dowell.com/a/products/chanpinpdf/IP5383.pdf

### 英集芯 IP5385（SoC）

- 介绍：支持 UFCS/PD3.0 的多串 SoC，适配 2–5 串。
- 特性：集成 H 桥升降压，多协议多口应用。
- 适用场景：中功率多口移动电源。
- 性能指标：家族中功率段；详见原厂/代理资料。
- 参考链接：方案页 https://www.sz-dowell.com/a/solution/848.html

### 英集芯 IP5365（SoC）

- 介绍：入门/中低功率移动电源 SoC，集成升降压与充电管理，PD3.0。
- 特性：同步升/降压；电量显示；多协议兼容。
- 适用场景：单串/小容量移动电源、工具附件电源。
- 性能指标：≤22.5W 档；1–4 串；QFN48。
- 参考链接：Datasheet4U https://datasheet4u.com/datasheet/Injoinic/IP5365-1549442

### 英集芯 IP5356M（SoC）

- 介绍：双向 PD3.0、多协议移动电源 SoC，集成升降压与充管。
- 特性：双向快充；多协议；I2C（家族特性）。
- 适用场景：单串小体积高性价比移动电源。
- 性能指标：放电≈22.5W、充电≈18W 档。
- 参考链接：电子发烧友介绍 https://m.elecfans.com/p/v106855.html

### 英集芯 IP5328P（SoC，EOL）

- 介绍：经典移动电源 SoC（已停产），集成 PD3.0/PPS 与升降压/充管、I2C、电量计。
- 特性：单电感升/降压；多口支持；PPS 输出；I2C/14bit ADC。
- 适用场景：存量/维护项目；参考旧案。
- 性能指标：18W 级典型；1–4 串。
- 参考链接：立创商城 https://item.szlcsc.com/200217.html

### 芯海 CPW6430（SoC）

- 介绍：芯海科技 140W 多口移动电源参考设计所用旗舰 SoC，集成同步升降压、电池管理与 PD3.1/UFCS/QC 协议控制，主打 8 串高功率移动储能。
- 特性：单芯片整合功率级、协议 MCU、±100mA 精密电流检测与多接口，单电感同步升降压效率最高 96%，支持多口功率调度。
- 适用场景：≥120W 移动电源、桌面电池底座、电动工具快速补能模块。
- 性能指标：支持 3–8 串锂/铁锂电池，输出最高 36V，展会 DEMO 指示功率 140W。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/1760005316165.html

#### 案例

- 2025（秋季）亚洲充电展芯海 140W 多口移动电源 Demo（同上链接）

### 智融 SW6318（SoC）

- 介绍：智融科技面向 2–3 串锂电与一体化充电器的多协议升降压 SoC，集成四开关 Buck-Boost 功率级、协议控制与库仑计。
- 特性：支持 PD3.0/PPS/AVS 及主流 UFCS/FCP/AFC 协议，内置电池检测通道、温感与 I2C 接口，可细粒度配置充放电电压电流。
- 适用场景：2–3 串笔电级移动电源、“充电器+移动电源”二合一、工具电池底座。
- 性能指标：支持双向 CC/CV 管理，充放电效率高，协议输出覆盖 5–28V 档（随应用配置）。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/1760005316165.html

### 智融 SW6301V / SW6302V / SW6303V / SW6308V（SoC 家族）

- 介绍：智融 100W 级多口升降压 SoC 组合，涵盖单 C、A+A+C、A+C+C 等端口形态，面向 2–6 串锂电与多口快充移动电源。
- 特性：输入 4–26V、输出 3.3–26V，可 10mV 步进调压；家族统一支持 PD3.1/UFCS 及多协议；内置 I2C 与 LED/188 数码管驱动，支持按键、小电流与功率配置。
- 适用场景：100W 以内多形态移动电源、车充一体移动电源、定制二合一快充。
- 性能指标：单芯片 100W 双向升降压，支持 2–6 串锂电；封装从 QFN5×5-40 至 QFN7×7-60 覆盖多端口需求。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/306583.html

### 智融 SW6306（SoC）

- 介绍：四口多协议升降压移动电源 SoC，PD3.1/UFCS，双向升降压，库仑计，I2C，可 2–6 串（NMC）/2–7 串（LFP）。
- 特性：输入 4–26V；输出 3.3–27.3V；10mV 步进；45µA Iq；I2C/MPPT/电量显示；多协议（PD3.1/UFCS/...）。
- 适用场景：≤100W 多口移动电源、磁吸/无线组合移动电源。
- 性能指标：≤100W；细粒度 AVS；多电池化学体系支持。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/325198.html

#### 案例

- 倍思 2024 BUFF 礼盒 30W 磁吸移动电源（采用 SW6306）
  - 来源：充电头网分解文（同上链接）

### 智融 SW6206S（SoC）

- 介绍：多口移动电源 SoC，支持 PD/UFCS 等多协议，主打多口任意口快充。
- 特性：多口配置（A+A+C+C）家族常见；协议丰富；SoC 方案。
- 适用场景：30–65W 多口移动电源。
- 性能指标：家族 22.5–65W 档（以具体版本为准）。
- 参考链接：相关阅读集合 https://www.chongdiantou.com/archives/325198.html

### 智融 SW6201 / SW6003（SoC）

- 介绍：入门功率段双向快充 SoC，适合 20–30W 档移动电源。
- 特性：SW6201 典型 22.5W，输入 4.5–13.5V、充电 5A 档（渠道页）；多协议；多口配置。
- 适用场景：小体积、低成本移动电源/定制礼赠类。
- 性能指标：20–30W 档，QFN40 5×5mm。
- 参考链接：B2B 规格页（SW6201）https://b2b.baidu.com/land?id=73aceccbe0466a1c60b3775c356b72c710

### 水芯电子 M12269/M12269H（SoC）

- 介绍：媒体报道的 PD3.1 双向 140W 多口 SoC，用于双 C 口 140W 场景。
- 特性：多口双向；PD3.1；SoC 方案。
- 适用场景：大功率移动电源/便携储能子系统。
- 性能指标：≤140W（报道口径）。
- 参考链接：腾讯新闻行业稿 https://news.qq.com/rain/a/20241010A02RD500

### 水芯电子 M12239（SoC）

- 介绍：水芯电子面向双路独立多口移动电源的 140W 级 SoC，集成同步升降压、电池管理、协议 MCU、电量计与显示驱动。
- 特性：支持 PD3.1、QC、AFC、FCP、SCP、UFCS 等多协议；内置 MCU、充放电管理、LED/188 数码管显示与多重保护；可扩展双通路输出来实现多口功率分配。
- 适用场景：3–8 串大功率移动电源、便携储能模块、车载/桌面双口快充底座。
- 性能指标：输入 3–8 串，输出 3.3–28V；最大输入输出功率 140W。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/1755859864832.html

#### 案例

- 倍思 优塔 ioTa 随行电户外移动电源 450W 参考设计解析（同上链接）

### 水芯电子 M12349（SoC）

- 介绍：水芯电子 C+A 双口独立升降压 SoC，集成 MCU、协议与功率级，支持 PD3.1 140W 双路功率动态分配。
- 特性：输入 42V、输出 3.3–28V/5A；内置同步升降压、协议控制、功率分配与显示驱动；支持双路独立快充与功率管理。
- 适用场景：高功率车充、多口桌面电源、移动电源多端口扩展。
- 性能指标：单口 140W，双路功率动态分配；支持多协议。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/1755859864832.html

#### 案例

- CE-LINK 双 USB-C 140W 快充车充 PDC140-2TGA（拆解）https://www.chongdiantou.com/archives/272584.html
- PHILIPS 飞利浦 165W 2C1A 快充车充 DLP4311B/93（拆解）https://www.chongdiantou.com/archives/278837.html

### 宝砾微 PL94056（SoC）

- 介绍：宝砾微集成升降压功率级与 PD 协议的双向 SoC，定位 1–6 串、双向充放的 100W 级移动电源/车充模块。
- 特性：内置四管全桥升降压、PD3.0/PPS/UFCS 等协议与 CC/DP/DM 高压隔离；I2C 管理多路电流电压监测，可编程 150/300kHz 开关频率。
- 适用场景：1C1A、2C1A 快充模块、车载快充、双向移动电源。
- 性能指标：VBUS/VBAT 3.6–32V，单芯片支持 ≤100W；支持 1–6 串 4.2V/3.5V 电池。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/306583.html

### 宝砾微 PL5501（升降压控制器，需协议 IC）

- 介绍：同步四开关升降压控制器，面向 140W PD3.1 模块，支持双向充放电并提供多频率/软启动配置。
- 特性：工作电压 3.6–32V；COT 架构；VADJ/IADJ 动态调节输出电压/电流；150/300/600/1200kHz 可选；内置 2A 栅驱与多项保护。
- 适用场景：140W 车充、桌面双向模块、移动电源功率级（需协议配合）。
- 性能指标：支持 5–28V 双向升降压、>100W；外围少，QFN4×4-32。
- 调压方式：模拟反馈（VADJ/IADJ 引脚）、外部补偿网络。
- 可配协议 IC：英集芯 IP2736U（PowerPi D140C 140W 方案）https://www.chongdiantou.com/archives/1754478170544.html。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/1755859864832.html

#### 案例

- PowerPi D140C PD3.1 140W 快充模块（PL5501 + IP2736U）https://www.chongdiantou.com/archives/1754478170544.html

### 宝砾微 PL5500H（升降压控制器，需协议 IC）

- 介绍：宝砾微面向 2C1A 车充与多口电源的双向升降压控制器，支持 3.6–32V 输入输出与多种保护。
- 特性：内置 2A 栅极驱动与模式平滑切换，支持抖频、可编程连续/轻载模式、输入输出逐周期限流。
- 适用场景：140W 车充模块、移动电源升降压级、储能充放电板。
- 性能指标：输入 3.6–32V、输出 2–32V；支持 1–6 串锂电；QFN4×4-32。
- 调压方式：VADJ/IADJ 模拟设定 + 外部反馈，支持离线配置。
- 可配协议 IC：英集芯 IP2756（C1 口 PD3.1 EPR）、慧能泰 HUSB382（C2/A）https://www.chongdiantou.com/archives/1751961283312.html。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/1755859864832.html

#### 案例

- 首诺信 140W 2C1A 车充方案（PL5500H + IP2756/HUSB382）https://www.chongdiantou.com/archives/1751961283312.html

### 南芯 SC8815A（升降压控制器，需协议 IC）

- 介绍：高效双向同步升降压控制器，支持 1–6 串、电池充电管理，I2C 可调，配 PD 协议 IC（如南芯 SC2006A）构成 PD 方案。
- 特性：I2C 调压与限流；10bit ADC；充电状态指示；欠压/过压/过流/短路/过温保护；QFN32。
- 适用场景：100W 级以上多口移动电源/便携电源（与协议 IC 组合）。
- 性能指标：1–6 串；双向升降压；系统功率随外围与热设计。
- 调压方式：I2C（支持协议 IC 侧 AVS 控制）；FB：按参考设计可接收外部设定。
- 可配协议 IC：南芯 SC2006A、英集芯/英飞凌等 PD 协议器件（视方案）。
- 参考链接：与非网/充电头网拆解 https://www.eefocus.com/article/1891360.html ，ChargerLAB https://www.chargerlab.com/teardown-of-huawei-superpower-100w-12000mah-power-bank-p0020/

#### 案例

- 华为 100W 12000mAh 全能充移动电源：双向快充（SC8815A + SC2006A）
  - 来源：充电头网 https://www.chongdiantou.com/archives/1760317355369.html ，EDN China https://www.ednchina.com/technews/36623.html
- EcoFlow RAPID Pro 230W：多路设计中 USB-C2 采用 SC8815A
  - 来源：ChargerLAB https://www.chargerlab.com/teardown-of-ecoflow-rapid-pro-230w-20000mah-power-bank-with-built-in-cable-ef-hb-100/

### 南芯 SC8721（升降压控制器，需协议 IC）

- 介绍：同步 4 开关升降压控制器，输入/输出 2.7–22V，支持 I2C 调压与限流，亦支持外部电阻设定，常配 PD 协议 IC 实现源端。
- 特性：I2C、电流检测、线损补偿、保护完备。
- 适用场景：18–65W 多口方案、适配器二次变换。
- 性能指标：2.7–22V I/O；功率依赖 MOS/电感与热设计。
- 调压方式：I2C / 外部电阻（FB）。
- 可配协议 IC：英集芯 IP2726、南芯 SC200x 等。
- 参考链接：联想相关拆解（充电头网）https://www.chongdiantou.com/archives/78270.html ，技术文 https://www.mwwr.cn/news/61908.html

### 南芯 SC8808（升降压控制器，需协议 IC）

- 介绍：南芯 80V 宽压双向升降压充电控制器，内置 MPPT 算法与高精度电流检测，面向高串储能与 PD3.1 EPR 输出。
- 特性：输入 4.5–80V、输出 5–48V，支持 16 串锂/18 串磷酸铁锂；I2C 或外部电阻配置电压电流；80–480kHz 可调并带抖频，充放电电流最高 50A。
- 适用场景：光伏储能充电、工具电池充电底板、高压 PD3.1 电源模块。
- 性能指标：千瓦级功率平台，±0.5% 电压 / ±3% 电流精度，峰值效率约 98%。
- 调压方式：I2C 配置 + 外部电阻预设（支持 Standalone）。
- 可配协议 IC：南芯 SC2001（双向 Type-C/PD DRP）https://www.chongdiantou.com/archives/347221.html。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/390901.html

### 南芯 SC8911（双向升降压充电芯片，需协议 IC）

- 介绍：全集成双向升降压充电芯片，面向 20–100W 家族功率段，配 PD/UFCS 协议构建设备端/源端。
- 特性：支持多模式切换与精细调压。
- 适用场景：多口移动电源、储能小模块。
- 性能指标：20–100W（家族覆盖）。
- 调压方式：I2C/FB（以具体版本为准）。
- 可配协议 IC：南芯 SC2006A/其它 PD 控制器。
- 参考链接：企业资讯 https://www.vertex-icbuy.com/qiyekuaibao/7374.html

### 南芯 SC8812A（1–4 串）/ SC8902A（1–3 串）（升降压控制器，需协议 IC）

- 介绍：面向 20–100W 档的双向升降压控制器，分别覆盖 1–4 串/1–3 串。
- 特性：双向升降压控制；I2C/FB；保护完备。
- 适用场景：中功率多串充放电管理。
- 性能指标：家族功率 20–100W。
- 调压方式：I2C/FB。
- 可配协议 IC：南芯 SC2006A、英集芯 IP27xx 等。
- 参考链接：企业资讯 https://www.vertex-icbuy.com/qiyekuaibao/7374.html

### 智融 SW7201（升降压控制器，需协议 IC）

- 介绍：高效率双向同步升降压控制器，1–4 串，支持 I2C，配协议 IC 可实现 ≤100W 双向快充。
- 特性：4 管架构、I2C、多路通路驱动、充电管理与升降压输出合一。
- 适用场景：35–100W 定制移动电源、工具电池座。
- 性能指标：≤100W、1–4 串。
- 调压方式：I2C（可配协议侧 AVS）。
- 可配协议 IC：智融 SW25xx/英集芯 IP27xx/英飞凌 CYPD 等（依方案）。
- 参考链接：方案文 https://blog.csdn.net/zxdzwj/article/details/130993776

### 维普创新 WP3236（升降压控制器，需协议 IC）

- 介绍：维普创新同步四开关升降压控制器，支持 PD3.1/AVS 输出，兼容 2.7–36V 输入与 2.7–28V 输出，可直接驱动 GaN 管。
- 特性：I2C 设置输出电压、输入/输出限流与开关频率；提供多重保护与紧凑 QFN32（4×4×0.75mm）封装。
- 适用场景：150W 级车充、桌面快充电源、双向 DC-DC 模块（需协议）。
- 性能指标：覆盖 5–28V 快充电压档，可扩展多通道功率。
- 调压方式：I2C AVS 调节 + 外部补偿。
- 可配协议 IC：智融 SW2335H（绿联 150W 3C1A 氮化镓车充 EC706）https://www.chongdiantou.com/archives/1739962273986.html。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/1755859864832.html

### 元芯半导体 YX2865（升降压控制器，需协议 IC）

- 介绍：元芯同步双向升降压控制器，覆盖 4–65V 输入/2–65V 输出，效率最高 98%，可驱动 GaN/Si FET，面向 PD3.1 240W 平台。
- 特性：50kHz–3MHz 可编程频率、可调死区时间、输入/输出限流与 ISMON 电流监测；DIR 引脚实现双向功流切换。
- 适用场景：240W PD3.1 适配器、便携储能、双向电池管理与工业 DC-DC。
- 性能指标：支持 1–14 串电池，双向升降压输出覆盖 5–48V EPR 档。
- 调压方式：外部补偿 / FB 网络 + 模拟限流设定。
- 可配协议 IC：立锜 RT7209（PD3.1 240W DRP 参考设计）https://www.chongdiantou.com/archives/1746776508718.html。
- 参考链接：充电头网 https://www.chongdiantou.com/archives/339051.html

#### 案例

- 元芯 + 立锜 RT7209 PD3.1 240W 双向平台（同上链接）

## 对比表

说明：类型列用于标识方案/调压方式：SoC / FB / I2C（若支持多种，列多项）。

| 类型    | 厂商                 | 型号/组合                 | 电池串数  | 协议/版本       | 典型/最大功率 | 关键特性                       | 参考链接                                                         |
| ------- | -------------------- | ------------------------- | --------- | --------------- | ------------- | ------------------------------ | ---------------------------------------------------------------- |
| SoC     | 英集芯               | IP2366                    | 2–6       | PD3.1           | ≤140W         | 集成同步升降压、I2C、双向快充  | https://www.chongdiantou.com/archives/1752118989918.html         |
| SoC     | 英集芯               | IP2368                    | 2–5       | PD3.0           | ≤100W(典)     | 四管 H 桥升降压，反放          | 同上                                                             |
| SoC     | 英集芯               | IP2363                    | 2–6       | PD3.1           | ≤140W         | 多串，家族覆盖                 | https://www.szjuquan.com/chanpin/lists_43_2.html                 |
| SoC     | 英集芯               | IP2369                    | 2–6       | PD3.1           | 45–100W 档    | 多串，PD3.1                    | https://b2b.baidu.com/land?id=5085acf2a30e716fcb8259784fc4580e10 |
| SoC     | 英集芯               | IP5383                    | 2–5       | PD3.0/UFCS      | ≤45W          | 集成 H 桥，多口                | https://www.chongdiantou.com/archives/1752118989918.html         |
| SoC     | 英集芯               | IP5385                    | 2–5       | UFCS/PD3.0      | —             | 多口 SoC                       | https://www.sz-dowell.com/a/solution/848.html                    |
| SoC     | 英集芯               | IP5365                    | 1–4       | PD3.0           | ≤22.5W        | 移动电源 SoC                   | https://datasheet4u.com/datasheet/Injoinic/IP5365-1549442        |
| SoC     | 英集芯               | IP5356M                   | 1–4       | PD3.0           | ≈22.5W 放电   | 双向快充                       | https://m.elecfans.com/p/v106855.html                            |
| SoC     | 英集芯               | IP5328P                   | 1–4       | PD3.0/PPS       | 18W 级        | 单电感升/降压+充电（EOL）      | https://item.szlcsc.com/200217.html                              |
| SoC     | 芯海                 | CPW6430                   | 3–8       | PD3.1/UFCS/QC   | 140W          | 三合一 SoC，96% 效率，36V 输出 | https://www.chongdiantou.com/archives/1760005316165.html         |
| SoC     | 智融                 | SW6318                    | 2–3       | PD3.0/PPS/AVS   | ≤100W         | 4 开关升降压、协议+库仑计      | https://www.chongdiantou.com/archives/1760005316165.html         |
| SoC     | 智融                 | SW6301V/6302V/6303V/6308V | 2–6       | PD3.1/UFCS      | ≤100W         | 多口 10mV AVS SoC、I2C 管理    | https://www.chongdiantou.com/archives/306583.html                |
| SoC     | 智融                 | SW6306                    | 2–6/2–7   | PD3.1/UFCS      | ≤100W         | 3.3–27.3V/10mV，I2C/库仑计     | https://www.chongdiantou.com/archives/325198.html                |
| SoC     | 智融                 | SW6206S                   | —         | PD/UFCS         | —             | 多口任意口快充                 | 见上文“相关阅读”                                                 |
| SoC     | 智融                 | SW6201/SW6003             | 入门      | PD              | —             | 入门段 SoC                     | 微信参考链接                                                     |
| SoC     | 水芯                 | M12269/H                  | 多串      | PD3.1           | ≤140W         | 双 C 口 140W（报道）           | https://news.qq.com/rain/a/20241010A02RD500                      |
| SoC     | 水芯                 | M12239                    | 3–8       | PD3.1/UFCS      | 140W          | MCU+协议一体，双路独立         | https://www.chongdiantou.com/archives/1755859864832.html         |
| SoC     | 水芯                 | M12349                    | —（车充） | PD3.1/双口      | 140W          | C+A 独立双口、功率分配         | https://www.chongdiantou.com/archives/1755859864832.html         |
| SoC     | 宝砾微               | PL94056                   | 1–6       | PD3.0/PPS/UFCS  | ≤100W         | 双向升降压 + 协议 SoC          | https://www.chongdiantou.com/archives/306583.html                |
| FB      | 宝砾微+英集芯        | PL5501 + IP2736U          | 1–6       | PD3.1（配协议） | 140W          | 四开关升降压，VADJ 动态调压    | https://www.chongdiantou.com/archives/1754478170544.html         |
| FB      | 宝砾微+英集芯/慧能泰 | PL5500H + IP2756/HUSB382  | 1–6       | PD3.1（2C1A）   | 140W+         | 3.6–32V 双向，抖频减 EMI       | https://www.chongdiantou.com/archives/1751961283312.html         |
| I2C     | 南芯+南芯            | SC8808 + SC2001           | ≤16       | PD3.1/AVS       | ≤1kW          | 80V 双向+MPPT，50A             | https://www.chongdiantou.com/archives/390901.html                |
| I2C, FB | 南芯+南芯            | SC8815A+SC2006A           | 多串      | PD              | ~100W         | 双向升降压+协议全套            | https://www.chongdiantou.com/archives/1760317355369.html         |
| I2C, FB | 南芯+英集芯/南芯     | SC8721+IP2726/SC200x      | 2.7–22V   | PD              | 18–65W 典     | I2C 调压/限流                  | https://www.chongdiantou.com/archives/78270.html                 |
| I2C, FB | 南芯+(协议)          | SC8911(+协议)             | 家族      | PD/UFCS         | 20–100W       | 全集成双向升降压               | https://www.vertex-icbuy.com/qiyekuaibao/7374.html               |
| I2C, FB | 南芯+(协议)          | SC8812A/SC8902A(+协议)    | 1–4/1–3   | PD              | 20–100W       | 双向升降压控制器               | https://www.vertex-icbuy.com/qiyekuaibao/7374.html               |
| I2C     | 智融+(协议)          | SW7201(+协议)             | 1–4       | PD              | ≤100W         | 双向同步升降压控制器           | https://blog.csdn.net/zxdzwj/article/details/130993776           |
| I2C     | 维普创新+智融        | WP3236 + SW2335H          | —（车载） | PD3.1           | ≤150W         | I2C AVS 升降压驱 GaN           | https://www.chongdiantou.com/archives/1739962273986.html         |
| FB      | 元芯+立锜            | YX2865 + RT7209           | 1–14      | PD3.1/EPR       | 240W          | 65V 双向升降压，98%            | https://www.chongdiantou.com/archives/1746776508718.html         |

注：表中“(典)”为典型设计功率；“组合”类需搭配相应 PD 协议 IC 才能实现完整源端 PD 功能。
