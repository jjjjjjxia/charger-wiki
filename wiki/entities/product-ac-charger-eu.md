# 欧标交流充电桩

> **类型**: entity (product)
> **创建时间**: 2026-07-20
> **最后更新**: 2026-07-23
> **来源**: [[raw/欧标/桩标准/IEC 61851-1-2017-1.md]], [[raw/欧标/随车充标准/IEC 62752 2024(1).md]], [[raw/漏电/IEC62955_2018.md]]
> **标签**: #欧标 #交流桩 #产品线

## 摘要

面向欧洲及部分亚太/中东市场的交流充电桩产品体系，执行 IEC 61851 / EN 系列标准。是海外出口的主力产品线，认证涉及 CE、CB 及多国转证。

## 详情

### 适用标准
- **IEC 61851-1:2017** (Ed.3.0) — 电动汽车传导充电系统 通用要求，详见 [[concepts/standard-iec-61851-1]]
  - 额定供电/输出电压：最高 1000V AC / 1500V DC
  - 核心充电模式：**Mode 3**（永久连接 AC 供电设备 + 控制导引），详见 [[concepts/charging-modes]]
- **IEC 62752:2024** (Ed.2.0) — IC-CPD（随车充）Mode 2 充电专用标准，详见 [[concepts/standard-iec-62752]]
  - 适用于便携式随车充产品（≤32A，单相≤250V/多相≤480V）
  - 新增强制温度控制（70°C/10s）、碾压测试、自检功能等
  - 与 IEC 61851-1 互补，详见 [[concepts/comparison-iec-61851-vs-62752]]
- **IEC 62955:2018** (Ed.1.0) — Mode 3 充电用直流剩余电流检测装置（RDC-DD），详见 [[concepts/standard-iec-62955]]
  - 适用于 Mode 3 充电桩的漏电保护补充装置
  - 额定直流剩余动作电流 IΔdc = 6mA，检测 Type A RCD 盲区的平滑直流剩余电流
  - 分类：RDC-MD（监测装置，配合外接断路器/RCD）和 RDC-PD（保护装置，集成一体）
  - 补充 IEC 61851-1 对直流剩余电流保护的要求缺口
- IEC 62196 (all parts) — 车辆接口/插头插座（Type 2）
- IEC 60529 — 外壳防护等级（IP Code）
- IEC 61543:2022 — RCD 的 EMC 要求（IC-CPD 引用）
- EN 61851-1 — IEC 61851-1 的欧洲转化版（CE 认证依据）
- ⏳ 待资料：EMC 标准（IEC 61851-21-2）、其他部件标准

### 产品特征
- 充电模式：Mode 3 为主（Case B/C 配置），Mode 2 为随车充产品线
- 接口类型：Type 2（IEC 62196-2）
- 防护等级：室内 ≥ IP41，室外 ≥ IP44（依据 [[concepts/safety-tests-iec-61851]]）
- Mode 2 随车充（IC-CPD）：功能盒 IP55，须符合 IEC 62752
- 额定参数：⏳ 待资料（具体型号的电压/电流/功率）

### 需做的认证
| 认证 | 性质 | 适用市场 | 状态 |
|------|------|---------|------|
| [[entities/certification-ce]] | 强制 | 欧盟 | ⏳ 待资料 |
| [[entities/certification-cb]] | 国际互认 | 多国转证基础 | ⏳ 待资料 |
| UKCA | 强制 | 英国 | ⏳ 待资料 |
| 多国转证 | — | 日/韩/澳/中东等 | ⏳ 待资料 |

## 关联
- 适用地区: [[entities/region-europe]]、[[entities/region-asia-pacific]]、[[entities/region-mea]]
- 相关概念: [[concepts/standard-iec-61851-1]]、[[concepts/standard-iec-62752]]、[[concepts/standard-iec-62955]]、[[concepts/charging-modes]]、[[concepts/safety-tests-iec-61851]]、[[concepts/comparison-iec-61851-vs-62752]]
- 参见: [[topics/certification-by-region]]

## 引用来源
- [1] [[raw/欧标/桩标准/IEC 61851-1-2017-1.md]] — 适用标准、充电模式、防护等级等核心技术要求
- [2] [[raw/欧标/随车充标准/IEC 62752 2024(1).md]] — IC-CPD 随车充产品标准（Mode 2 充电）
- [3] [[raw/漏电/IEC62955_2018.md]] — IEC 62955:2018 RDC-DD 直流剩余电流检测装置（Mode 3 充电漏电保护）

## 变更记录
- 2026-07-20: 初始创建，搭建产品骨架
- 2026-07-22: 填充适用标准（IEC 61851-1:2017）、充电模式（Mode 3）、防护等级等，来源 [[raw/欧标/桩标准/IEC 61851-1-2017-1.md]]
- 2026-07-23: 新增 IEC 62752:2024 随车充标准、Mode 2 产品线信息，来源 [[raw/欧标/随车充标准/IEC 62752 2024(1).md]]
- 2026-07-23: 新增 IEC 62955:2018 RDC-DD 漏电保护标准引用，来源 [[raw/漏电/IEC62955_2018.md]]
