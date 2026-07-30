# BACL 充电桩各国认证要求指南

> **类型**: topic
> **创建时间**: 2026-07-30
> **最后更新**: 2026-07-30
> **来源**: [[standards/bacl-ev-charger-safety-certification|BACL 充电桩各国认证要求全文]]

## 摘要

本页编译自 BACL（倍科）发布的《充电桩 EV Charger 各国认证要求》指南（Jeanne Han，2024-05-30）。该指南从**认证机构视角**系统梳理了充电桩（EV Charger）进入全球各市场的准入维度、对应标准与认证标志，是连接本 wiki 各标准概念页与地区性认证的导航性主题页[1]。

指南将充电桩全球准入划分为若干维度：安规（Safety）、EMC/RF、并网（Grid connection）、能效（Energy efficiency）、及其他（如有害物质、计量）等。核心技术标准覆盖 **UL 北美系列**、**IEC/EN 61851 系列**、**IEC 62196 连接器系列**、**ISO/IEC 15118** 与 **DIN SPEC 70121**、**SAE J1772**、**GB/T 20234** 等[1]。

> 注：原始指南含大量机构标志、流程与表格截图，本页仅提取并整理其文字性事实；图片未随仓库提供，未作复制。文中所列认证标志/机构名称均按指南原文转述。

## 详情

### 一、充电桩全球准入维度

指南将准入要求分为以下类别[1]：
- 安规认证（Safety）
- 全球准入安规标准
- EMC / RF 标准
- 并网认证标准（Grid connection）
- 能效认证标准（Energy efficiency）
- 其他标准（有害物质、计量等）

### 二、北美 UL 系列标准（指南 §03）

指南对北美标准单独成章，涵盖[1]：
- **UL 2231-1**：人身保护系统通用要求——主要范围与重要定义（CCID/GM-I/IM-I 等）
- **UL 2231-2**：装置特殊要求——结构、性能、制造与生产线测试、额定值、标记
- 与 [[concepts/standard-ul-2594]]（AC EVSE）、[[concepts/standard-ul-2202]]（DC 快充）、[[concepts/standard-ul-1998]]（可编程组件软件）共同构成北美 EVSE 认证标准体系

### 三、IEC/EN 61851 系列（指南 §02）

指南对 IEC 61851 系列分章梳理，重点包括[1]：
- **IEC 61851-1**：适用范围、分类、结构要求、测试要求、标签与说明书要求
- 直流充电相关的 [[concepts/standard-iec-61851-23]]（DC 充电站，Mode 4）
- 车外/车载 EMC：[[concepts/standard-iec-61851-21-2]] 与 [[concepts/standard-iec-61851-21-1]]

### 四、充电系统配置与连接器（指南 §CCS）

指南给出 IEC/EN 61851-23 附录系统（System A/B/C）与 IEC 62196-3 连接器配置的对应关系[1]：

| 连接器配置 | 额定 | 充电系统 | 指南标注适用地区 |
|------|------|------|------|
| IEC/EN 62196-3 配置 AA | 600 V, 200 A | System A（Annex AA） | 日本 |
| IEC/EN 62196-3 配置 BB | 750 V, 250 A | System B（Annex BB） | 中国 |
| IEC/EN 62196-3 配置 EE（Combo1）/ FF（Combo2） | 1000 V, 200 A | System C（Annex CC） | 欧洲、北美、韩国等 |

> 注：上表"适用地区"系 BACL 指南原文表述；其中部分对应关系（如配置 BB 对应中国）与国标体系（GB/T 20234）实践可能存在差异，落地时应以目标市场最新法规为准。

- **联合充电系统（CCS）**：基于开放通用 EV 标准（IEC 61851、IEC 62196、ISO/IEC 15118、DIN SPEC 70121）。直流采用 IEC 62196-3 的 "combo 2"，依据 **ISO 15118** 和/或 **DIN SPEC 70121** 提供车网通信接口；交流采用 IEC 62196-2 的 **Type 2** 插头，并符合 IEC 61851-1（Annex A）与 ISO 15118（适用时）的控制导向通信。交流最大约 **43 kW** 三相快速充电，直流最大 **200 kW**（展望 350 kW）[1]

### 五、各地区认证要求（指南 §全球准入）

**欧盟 / 英国[1]：**
- 安全、EMC、无线分别依据 **CE** 标志下的指令：LVD **2014/35/EU**、EMC **2014/30/EU**、RED **2014/53/EU**
- 有害物质：REACH **(EC) No 1907/2006**、RoHS **2011/65/EU**
- 英国：**UKCA** 认证；并有 **PEN 法规**（electric vehicle smart charge points，电动汽车智能充电点）要求

**美国 / 加拿大[1]：**
- 安全：美国 **OSHA NRTL**（国家认可实验室）、加拿大 **SCC**
- EMC：美国 **FCC**、加拿大 **ICES**
- 其他：需当地进口商；能效 **Energy Star**；加州计量 **CTEP**；加州环保 **TP65**

**日本[1]：**
- **CQC** 认证
- 充电桩本身不在强制范围；**插头、输入线、控制盒、输出线、连接器**需 **PSE** 认证
- 自愿性认证：**JET** 或 **EVSE 认证（JARI）**、**CHAdeMO**
- 无线：**SRRC/NAL** 认证（标识 CMIIT ID）；**JRF** 认证

**韩国[1]：**
- **KC 安全确认**（韩国发证机构）；**KC** 认证；需在韩国当地授权实验室测试

**其他市场（指南列举）[1]：**
- 阿根廷：ENACOM；巴西：ANATEL，AC 50 V 以上 / DC 75 V 以上产品在强制范围内（S-Mark）；墨西哥：NOM、IFETEL；智利：SUBTEL；马来西亚：SIRIM；泰国：NBTC；菲律宾：ICC/PS、NTC（Output power < 60 mW EIRP 豁免）；澳大利亚：CoS 安全认证、RCM 等

### 六、交流充电桩零部件认证（指南 §05）

指南单列"交流充电桩零部件认证要求"与"充电桩关键技术参数 CDF（关键件清单）"，强调关键零部件（如插接件、电缆、控制板）须随整机一并满足对应标准与认证可追溯性[1]。

## 关联

- [[concepts/standard-ul-2594]] / [[concepts/standard-ul-2202]] / [[concepts/standard-ul-2231-1]] / [[concepts/standard-ul-2231-2]] / [[concepts/standard-ul-1998]] — 北美 EVSE 认证标准族
- [[concepts/standard-iec-61851-1]] / [[concepts/standard-iec-61851-23]] / [[concepts/standard-iec-61851-21-1]] / [[concepts/standard-iec-61851-21-2]] — IEC/EN 体系
- [[concepts/standard-sae-j1772]] — 北美交流接口（对应指南中 Type 1 体系）
- [[concepts/standard-gb-2099-7]] / [[concepts/standard-gb-39752]] — 中国国标体系相关
- [[concepts/certification-ce]] / [[concepts/certification-ccc]] / [[concepts/certification-cqc]] / [[concepts/certification-cb]] / [[concepts/region-north-america]] — 地区与认证标志导航

## 引用来源

[1] [[standards/bacl-ev-charger-safety-certification|BACL 充电桩各国认证要求全文]] — §01 认证简介（准入维度）、§02 IEC/EN 61851 系列、§03 北美 UL 系列、§CCS 系统 A/B/C 与连接器配置、§全球准入（欧盟 CE/UKCA/REACH/RoHS、美国 NRTL/FCC/Energy Star、日本 CQC/PSE/CHAdeMO、韩国 KC、及其他市场）、§05 零部件与 CDF

## 变更记录

- 2026-07-30：初始化本 topic 页，编译 BACL《充电桩各国认证要求》指南的全球准入维度、北美 UL 系列、IEC/EN 61851 系列、CCS/系统 A-B-C 配置，以及欧盟/美加/中日韩等地区的认证标志与主管要求。已注明图片未复制、地区映射按指南原文转述。
