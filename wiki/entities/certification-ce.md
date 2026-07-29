# CE 认证 — 欧盟符合性标志

> **类型**: entity (certification)
> **创建时间**: 2026-07-20
> **最后更新**: 2026-07-22
> **来源**: [[standards/iec-61851-1-2017-part1|IEC 61851-1:2017 全文]]
> **标签**: #CE #强制认证 #欧盟

## 摘要

CE 标志是产品进入欧盟市场的强制性合格评定标志，表明产品符合欧盟相关指令/法规的安全、健康、环保要求。交流充电桩进入欧盟成员国须取得 CE 认证。

> ⏳ 以上为行业常识性描述，具体适用指令、测试标准、符合性评定路径需以 `raw/` 资料核实。

## 详情

### 认证性质
- 强制性（欧盟市场准入）
- 适用市场: 欧盟成员国

### 适用指令/法规
- LVD（低电压指令 2014/35/EU）— 安规评估依据 **EN 61851-1**（IEC 61851-1 的欧洲转化版）
- EMC（电磁兼容指令 2014/30/EU）— ⏳ 待资料：具体 EMC 标准
- RED（无线电设备指令 2014/53/EU）— 如有通信功能则适用
- ⏳ 待资料：其他适用指令（如 ErP 能效等）

### 适用产品
- [[entities/product-ac-charger-eu]]

### 认证流程
- 安规测试依据：[[concepts/standard-iec-61851-1]]（EN 61851-1）
- 通用流程框架参见: [[topics/certification-process-overview]]
- ⏳ 待资料：自我声明 vs. 公告机构介入路径、所需技术文件清单

### 测试项目
基于 EN 61851-1（= IEC 61851-1）的安规测试，详见 [[concepts/safety-tests-iec-61851]]：
- IP 防护等级（室内 IP41 / 室外 IP44）
- 绝缘电阻（Class I > 1MΩ / Class II > 7MΩ）
- 接触电流（Class I ≤ 3.5mA / Class II ≤ 0.25mA）
- 介电耐压（Class I: Un+1200V / Class II: 2×(Un+1200V)）
- 温升（IEC TS 61439-7）
- 湿热功能测试、低温功能测试
- 残余电流保护（RCD ≤ 30mA，Type A/B）

### 与 CB 的关系
- CB 报告常作为 CE 认证的技术支撑，详见 [[entities/certification-cb]]

### 证书维护
- ⏳ 待资料

## 关联
- 适用产品: [[entities/product-ac-charger-eu]]
- 适用地区: [[entities/region-europe]]
- 相关认证: [[entities/certification-cb]]
- 测试依据: [[concepts/standard-iec-61851-1]]、[[concepts/safety-tests-iec-61851]]
- 参见: [[topics/certification-by-region]]、[[topics/certification-process-overview]]

## 引用来源
- [1] [[standards/iec-61851-1-2017-part1|IEC 61851-1:2017 全文]] — 安规测试依据标准（EN 61851-1 的 IEC 原版），测试项目参数

## 变更记录
- 2026-07-20: 初始创建，搭建认证骨架
- 2026-07-22: 填充适用指令（LVD/EMC/RED）、测试项目（IP/绝缘/耐压/温升/湿热/RCD），来源 [[standards/iec-61851-1-2017-part1|IEC 61851-1:2017 全文]]
