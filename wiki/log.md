# 变更日志 — 充电桩产品认证知识库

## 2026-07-20

### 初始化
- 🏗️ **初始化**: 创建知识库目录结构（`raw/`、`wiki/entities/`、`wiki/concepts/`、`wiki/topics/`）
- 📜 **新建**: `SCHEMA.md` — 定义产品体系（国标/欧标/美标）、认证分类（CCC/CQC/CE/CB/多国）、地区划分、查询路径约定、命名规范、质量红线
- 📑 **新建**: `wiki/index.md` — 索引框架
- 🧭 **规划**: 确立三条查询路径——按地区查 / 按认证查 / 按产品查

### 骨架页面创建
- ✨ **新增**: [[entities/product-ac-charger-cn]] — 国标交流充电桩骨架
- ✨ **新增**: [[entities/product-ac-charger-eu]] — 欧标交流充电桩骨架
- ✨ **新增**: [[entities/product-ac-charger-us]] — 美标交流充电桩骨架
- ✨ **新增**: [[entities/certification-ccc]] — CCC 认证骨架
- ✨ **新增**: [[entities/certification-cqc]] — CQC 认证骨架
- ✨ **新增**: [[entities/certification-ce]] — CE 认证骨架
- ✨ **新增**: [[entities/certification-cb]] — CB 认证骨架
- ✨ **新增**: [[entities/region-china]] — 中国大陆地区骨架
- ✨ **新增**: [[entities/region-europe]] — 欧洲地区骨架
- ✨ **新增**: [[entities/region-north-america]] — 北美地区骨架
- ✨ **新增**: [[entities/region-asia-pacific]] — 亚太其他地区骨架
- ✨ **新增**: [[entities/region-mea]] — 中东/非洲地区骨架
- ✨ **新增**: [[topics/certification-by-region]] — 按地区查认证（主导航入口）
- ✨ **新增**: [[topics/certification-process-overview]] — 认证流程总览

### 交叉引用建立
- 🔗 [[entities/product-ac-charger-cn]] ↔ [[entities/certification-ccc]]、[[entities/certification-cqc]]、[[entities/region-china]]
- 🔗 [[entities/product-ac-charger-eu]] ↔ [[entities/certification-ce]]、[[entities/certification-cb]]、[[entities/region-europe]]
- 🔗 [[entities/product-ac-charger-us]] ↔ [[entities/region-north-america]]
- 🔗 [[entities/certification-cb]] ↔ [[entities/certification-ce]]（CB 转 CE 路径）
- 🔗 [[topics/certification-by-region]] ↔ 所有地区页与认证页
- 🔗 [[topics/certification-process-overview]] ↔ 所有认证实体页

### 当前状态
- ✅ 骨架搭建完成（14 个页面）
- ⏳ `raw/` 目录待用户投放原始资料（认证规范、测试报告、流程文档等），到位后开始编译填充具体认证数据

> 下一步：用户投放资料至 `raw/` → LLM 执行 ingest 编译 → 填充各页面具体内容（测试项目、周期、费用、机构）→ 创建国家页与多国认证页 → 补充概念页。

## 2026-07-22

### Ingest: IEC 61851-1:2017 安规标准

> 来源: `raw/欧标/桩标准/IEC 61851-1-2017-1.md`（292页，IEC 61851-1 Edition 3.0）

#### 新增概念页
- ✨ **新增**: [[concepts/standard-iec-61851-1]] — IEC 61851-1:2017 标准详解（基本信息、范围、结构16章+附录、关键引用文件）
- ✨ **新增**: [[concepts/charging-modes]] — 充电模式 Mode 1-4（定义、限值、各国限制、强制功能、控制导引）
- ✨ **新增**: [[concepts/safety-tests-iec-61851]] — 安规测试项目详解（IP等级、绝缘电阻、接触电流、介电耐压、温升、湿热、低温、RCD）

#### 更新实体页
- 📝 **更新**: [[entities/product-ac-charger-eu]] — 填充适用标准（IEC 61851-1:2017）、充电模式（Mode 3）、防护等级
- 📝 **更新**: [[entities/certification-ce]] — 填充适用指令（LVD/EMC/RED）、安规测试项目清单
- 📝 **更新**: [[entities/certification-cb]] — 填充测试标准（IEC 61851-1:2017）、安规测试引用
- 📝 **更新**: [[entities/region-europe]] — 填充各国充电模式差异（UK/IT/FR/NO/CH/DK/DE）
- 📝 **更新**: [[topics/certification-process-overview]] — 填充 CE/CB 安规测试依据与项目引用

#### 交叉引用建立
- 🔗 [[concepts/standard-iec-61851-1]] ↔ [[entities/product-ac-charger-eu]]、[[entities/certification-ce]]、[[entities/certification-cb]]
- 🔗 [[concepts/charging-modes]] ↔ [[concepts/standard-iec-61851-1]]、[[entities/region-europe]]
- 🔗 [[concepts/safety-tests-iec-61851]] ↔ [[entities/certification-ce]]、[[entities/certification-cb]]、[[topics/certification-process-overview]]

#### 关键编译内容
- 充电模式：Mode 1（16A/无导引，部分国家禁止）、Mode 2（32A/便携保护）、**Mode 3（永久连接+导引，交流桩主力）**、Mode 4（DC）
- 安规测试参数：IP41(室内)/IP44(室外)、绝缘>1MΩ(Class I)/>7MΩ(Class II)、接触电流≤3.5mA/0.25mA、AC耐压(Un+1200V)、RCD≤30mA Type A/B
- 欧洲国家差异：UK禁Mode 1、IT公共区禁Mode 1/2、FR限8A、CH限16A等

### 当前状态
- ✅ 总页面数: 17（14 骨架 + 3 新概念页）
- ✅ 首次 ingest 完成：IEC 61851-1:2017 安规标准已编译
- ⏳ 待补充：认证流程步骤/周期/费用、EMC标准、接口标准(IEC 62196)、国标充电标准、国家页、多国认证页

> 下一步：继续投放 CCC/CQC 国标资料、CE/CB 认证流程资料、各国认证要求资料至 `raw/`。

### MkDocs 站点部署

- 🌐 **搭建**: 基于 MkDocs Material 主题构建知识库静态站点，支持中文全文搜索、双向链接跳转、暗色模式切换
- 📄 **新增**: `wiki/guide.md` — 团队使用指南页（三种查询方式 + 速查表 + 搜索技巧 + 维护说明）
- ⚙️ **配置**: `mkdocs.yml` — 文档目录(wiki/)、Material 主题(teal/amber 配色)、roamlinks 插件(处理 `[[wiki link]]`)、导航结构(8个分组)
- 🔧 **适配**: index.md 表格内 `\|` 别名链接改为标准 Markdown 链接（roamlinks 不兼容转义竖线）
- ☁️ **部署**: 静态站点部署至 CloudStudio sandbox，团队可通过 URL 多人访问
- 🔗 **访问地址**: `https://d7e44838e3d14cbb8f00d805e174d560.app.codebuddy.work`

> 持续更新流程：投放资料至 `raw/` → LLM ingest 编译 → `mkdocs build` 重新构建 → 重新部署至云端

## 2026-07-22（续）

### Ingest: GB 39752-2024 + GB 44263-2024 国标安规标准

> 来源: `raw/国标/GB 39752-2024 电动汽车供电设备安全要求.md`（31页，强制性国标）、`raw/国标/GB 44263-2024 电动汽车传导充电系统安全要求_unlocked.md`（35页，强制性国标）

#### 新增概念页
- ✨ **新增**: [[concepts/standard-gb-39752]] — GB 39752-2024 供电设备安全要求（强制标准、安全要素全表、试验方法、标准实施过渡期）
- ✨ **新增**: [[concepts/standard-gb-44263]] — GB 44263-2024 充电系统安全要求（充电模式条件、接口安全、交直流充电安全、测试项目清单）
- ✨ **新增**: [[concepts/comparison-gb-vs-iec-safety]] — ⚡国标 vs IEC 61851 安规参数对比（7维度对比，4处矛盾标注，设计建议）

#### 更新实体页
- 📝 **更新**: [[entities/product-ac-charger-cn]] — 填充适用标准（GB 39752/44263）、产品安全参数（IP54/32、10MΩ、30mA RCD）
- 📝 **更新**: [[entities/certification-ccc]] — 填充认证依据标准、测试项目清单、过渡期信息（2025-08-01/2026-08-01）
- 📝 **更新**: [[entities/region-china]] — 填充强制标准实施时间线、1年过渡期信息

#### 交叉引用建立
- 🔗 [[concepts/standard-gb-39752]] ↔ [[concepts/standard-gb-44263]]（配套标准：设备安全+系统安全）
- 🔗 [[concepts/standard-gb-39752]] ↔ [[entities/product-ac-charger-cn]]、[[entities/certification-ccc]]
- 🔗 [[concepts/comparison-gb-vs-iec-safety]] ↔ [[concepts/standard-gb-39752]]、[[concepts/standard-iec-61851-1]]
- 🔗 [[entities/product-ac-charger-cn]] ↔ [[entities/product-ac-charger-eu]]（通过对比页关联）

#### ⚠️ 矛盾标注（4处）
- ⚠️ 防护等级：国标室内 IP32 vs IEC IP41（防尘/防水各有高低）
- ⚠️ 绝缘电阻：国标常态 10MΩ vs IEC 1MΩ(I类)/7MΩ(II类)（国标更严）
- ⚠️ 介电耐压：国标分档表 vs IEC 公式(Un+1200V)（表述不同，数值有差异）
- ⚠️ 湿热试验：国标 2循环(约2天) vs IEC 室外24天（IEC 更严）

#### 关键编译内容
- 两个强制标准配套：GB 39752(设备) + GB 44263(系统)，产品须同时满足
- 标准实施：新申请 2025-08-01 执行，已有报告 2026-08-01 执行（1年过渡期）
- 国标安全参数：IP54(室外)/IP32(室内)、绝缘≥10MΩ(常态)、RCD≤30mA(A型+6mA DC/B型)
- 充电模式：国标明确禁止 Mode 1，Mode 2 限流（10A→8A/16A→16A/32A→32A）
- 交直流充电安全：控制导引、PWM供电能力声明、CC/CP回路保护、供电网断电≤30V/0.2J

### 当前状态
- ✅ 总页面数: 20（14 骨架 + 6 概念页）
- ✅ 国标安规标准已编译：GB 39752 + GB 44263 + 对比页
- ✅ 知识库已覆盖：国标体系 + 欧标体系 + 两者对比
- ⏳ 待补充：CCC/CQC 认证流程（送检步骤/周期/费用/机构）、EMC标准、接口标准、国家页、多国认证页

> 下一步：继续投放认证流程文档、EMC标准、接口标准、各国认证要求至 `raw/`。

### 站点修复

- 🔧 **修复**: `use_directory_urls: false` — CloudStudio 静态服务器不兼容 MkDocs 默认目录式 URL（`/page/index.html`），改为扁平文件（`/page.html`），所有子页面可正常访问

## 2026-07-22（续二）

### Ingest: GB/T 18487.1-2023 传导充电系统通用要求

> 来源: `raw/国标/GB_T 18487.1-2023 电动汽车传导充电系统　第1部分：通用要求.md`（160页，推荐性国标，代替 2015 版，2024-04-01 实施）

#### 新增概念页
- ✨ **新增**: [[concepts/standard-gb-t-18487-1]] — GB/T 18487.1-2023 通用要求详解（范围、分类体系、充电模式、电击防护、性能要求、结构要求、使用条件、附录体系、与2015版变化）

#### 更新概念页
- 📝 **更新**: [[concepts/comparison-gb-vs-iec-safety]] — 补全接触电流限值（此前标注"待核实"现已填充）、介电强度来源说明、新增 GB/T 18487.1 引用
- 📝 **更新**: [[concepts/charging-modes]] — 补充国标 GB/T 18487.1 充电模式定义、连接方式D/E、国标新增充电唤醒功能

#### 更新实体页
- 📝 **更新**: [[entities/product-ac-charger-cn]] — 补充 GB/T 18487.1 通用标准引用、实施日期
- 📝 **更新**: [[entities/certification-ccc]] — 补充 GB/T 18487.1 认证依据、通用性能测试项目
- 📝 **更新**: [[entities/certification-cqc]] — 填充认证依据标准、测试项目引用（从⏳升级为✅）

#### 交叉引用建立
- 🔗 [[concepts/standard-gb-t-18487-1]] ↔ [[concepts/standard-gb-39752]]、[[concepts/standard-gb-44263]]（国标标准体系三件套）
- 🔗 [[concepts/standard-gb-t-18487-1]] ↔ [[entities/certification-ccc]]、[[entities/certification-cqc]]（认证依据）
- 🔗 [[concepts/comparison-gb-vs-iec-safety]] ↔ [[concepts/standard-gb-t-18487-1]]（对比页新增来源）

#### 关键编译内容
- GB/T 18487.1-2023 为充电系统**基础通用标准**，虽为推荐性（GB/T）但被 CCC/CQC 认证体系引用
- 充电模式：国标明确**禁止 Mode 1**，与 IEC 部分国家限制不同
- 性能要求：接触电流限值与 IEC 基本一致（正常0.5mA AC/故障3.5mA AC）
- 绝缘电阻：常态 ≥10MΩ（500V DC），湿热后 I类>1MΩ / II类>7MΩ
- 介电强度：分档表（60<Ui≤300 → 1500V AC / 2120V DC），与 GB 39752 一致
- 冲击耐压：500-6000V（按系统标称电压分档）
- RCD：IΔn ≤ 30mA，A型+6mA DC / B型
- IP防护：Mode 3/4 室内 IP32 / 室外 IP54
- 新增功能：充电唤醒、V2G、连接方式D/E、接触器粘连

#### ✅ 此前"待核实"项已补全
- 对比页§6 接触电流：GB/T 18487.1 §12.1 限值与 IEC 基本一致，已从"⏳待核实"更新为完整参数表

### 当前状态
- ✅ 总页面数: 21（14 骨架 + 7 概念页）
- ✅ 国标标准体系完整：GB 39752 + GB 44263 + GB/T 18487.1 + 对比页
- ✅ 知识库已覆盖：国标体系（强制+推荐）+ 欧标体系 + 两者对比
- ⏳ 待补充：CCC/CQC 认证流程（送检步骤/周期/费用/机构）、EMC标准、接口标准、国家页、多国认证页

> 持续更新流程：投放资料至 `raw/` → LLM ingest 编译 → `mkdocs build` 重新构建 → 重新部署至云端

## 2026-07-22（续三）

### 完整性审查：4份标准全文编译补全

> 用户要求："确定一下这个知识库是把我投喂给你的材料的所有内容和文字都吸收了哦，不然会有误导的"
> 对已编译的4份标准（IEC 61851-1、GB 39752、GB 44263、GB/T 18487.1）进行系统性完整性审查，补全遗漏内容。

#### 审查方法
- 两个并行 Agent 逐章对比源文件提取文本与 wiki 页面内容
- 识别遗漏章节、缺失参数、覆盖面不足的区域
- 已编译的数值参数准确性良好，主要问题是覆盖面不足

#### 📝 更新: [[concepts/standard-iec-61851-1]] — 补全10个遗漏章节
- §3 术语定义（约50个术语，4大类）
- §8.2 存储能量（60V/50μC 和 60V/0.2J 阈值）
- §8.3 故障保护（4种保护措施）
- §8.4 保护导体（各模式要求）
- §11 电缆组件要求（电气额定值/介电/结构/尺寸/应力释放/存储）
- §12.2 机械开关器件特性（开关/接触器/断路器/继电器/涌入电流）
- §12.3 电气间隙和爬电距离（过电压类别 IV/III/II）
- §12.11 机械强度（Mode 2 IK08）
- §13 过载和短路保护（I²t: 75,000/80,000 A²s）
- §16 标志和说明（安装手册/用户手册/设备标志/电缆标志/耐久性测试）

#### 📝 更新: [[concepts/safety-tests-iec-61851]] — 填充机械强度
- §12.11 机械强度详细要求（IK08 + 测试后判定标准）

#### 📝 更新: [[concepts/standard-gb-39752]] — 补全3个遗漏章节
- §5.5 过热及着火（表面温度限值: 50/60/60/85/77°C + 引燃防护）
- §5.7 电磁兼容（抗扰度 + 发射要求，引用 GB/T 18487.2）
- 附录A 安装要求（A.1-A.5: 安装/配电系统/配电线路/防火/接地）

#### 📝 更新: [[concepts/standard-gb-44263]] — 补全2个遗漏章节
- §8.2 直流充电异常保护详细参数（§8.2.1-8.2.9: 通信超时/CC1回路/供电回路/过压/过流/负载突降的完整时间参数和电流限值）
- §10 标准实施过渡期（新申请 2025-08-01 / 已有报告 2026-08-01）

#### 📝 更新: [[concepts/standard-gb-t-18487-1]] — 补全4个遗漏章节
- §7.4 保护接地导体（Mode 4 导体截面: 16mm²/6mm²）
- §10.7 冲击电流（Mode 2/3: 230A/100μs + 30A/1s; Mode 4: ≤20A DC）
- §11.7/§12.6 SPD 电涌保护器（选配场景 + 输入端瞬态过压限值 + 雷电防护）
- §13 过载保护和短路保护（I²t: 75,000/80,000/500,000 A²s，含 Mode 4 新增值）

#### 📝 更新: [[concepts/comparison-gb-vs-iec-safety]] — 从7维度扩展至15维度
新增8个对比维度：
- §8 机械强度 IK 等级（国标 IK10/IK08 vs IEC IK08）
- §9 短路保护 I²t 限值（国标新增 Mode 4: 500,000 A²s）
- §10 冲击电流（参数一致，国标新增 Mode 4: 20A DC）
- §11 保护接地导体（国标更具体: 16mm²/6mm²）
- §12 电涌保护器 SPD（国标新增，IEC 未对应规定）
- §13 过热及着火（国标明确温度限值，IEC 引用间接规定）
- §14 存储能量（国标更严: 1s/30V vs IEC 5s/60V）
- §15 标准实施过渡期（国标1年过渡期，IEC 无过渡期）
- 更新设计建议（新增5条针对性建议）

#### 新增矛盾标注
- ⚠️ 机械强度：IEC 仅 Mode 2 明确 IK08，Mode 3/4 通过引用间接规定；国标直接明确 IK10(金属)/IK08(非金属)
- ⚠️ Mode 4 I²t：国标新增 500,000 A²s，IEC 未覆盖
- ⚠️ 存储能量：永久连接设备断电，国标 1s/30V 比 IEC 5s/60V 更严
- ⚠️ SPD：国标新增要求，IEC 61851-1 未对应规定

### IEC 62752-2024 随车充标准 — OCR 提取中

> 来源: `raw/欧标/随车充标准/IEC 62752 2024(1).pdf`（162页）
> PDF 使用自定义字体编码，pypdf/pymupdf/pdfplumber/pdftotext 四种工具提取均为乱码
> 已将162页渲染为150 DPI PNG图片，使用 rapidocr-onnxruntime 进行 OCR 提取
> OCR 完成后将编译进 wiki 页面

## 2026-07-23

### IEC 62752:2024 OCR 提取与编译
- ✅ **OCR完成**: 162页全部 OCR 提取完成（rapidocr-onnxruntime，约35分钟），输出至 `raw/欧标/随车充标准/IEC 62752 2024(1).md`（约7200行）
- ✨ **新增**: [[concepts/standard-iec-62752]] — IEC 62752:2024 IC-CPD 随车充标准概念页
  - 全文编译：适用范围、术语定义、分类（4.1-4.6）、特性参数（Table 1-4）、标志信息、标准工作条件
  - 构造要求（§8.1-8.25）：温度控制70°C/10s、IP55、电缆截面Table 6、电气间隙Table 7、温升Table 8、自检功能
  - 测试要求（§9.1-9.36）：36项型式试验、介电性能、短路试验Table 17、EMC Table 20、碾压5000N/11000N、低温-40°C、振动2G、温度控制验证
  - 附录A-G概要
- ✨ **新增**: [[concepts/comparison-iec-61851-vs-62752]] — IEC 61851-1 vs IEC 62752 对比分析
  - 10维度对比：适用范围、产品定义、RCD、控制导引、温度保护、机械强度、短路保护、自检功能、EMC、特殊环境
  - 标准关系图：IEC 61851-1 → Mode 2 → IEC 62752 引用关系
  - 设计建议8条
- 📝 **更新**: [[entities/product-ac-charger-eu]] — 新增 IEC 62752 适用标准、Mode 2 产品线信息
- 🔗 **链接**: [[concepts/standard-iec-62752]] ↔ [[concepts/standard-iec-61851-1]] ↔ [[concepts/comparison-iec-61851-vs-62752]]
- 🔗 **链接**: [[entities/product-ac-charger-eu]] ↔ [[concepts/standard-iec-62752]]
- ⚠️ **矛盾标注**: IEC 61851-1 仅要求 Type A RCD，而 IEC 62752 要求 DC 6mA 检测（更严格）
- 📊 **索引更新**: 总页面数 21→23，概念页 7→9

### Ingest: IEC 62955:2018 RDC-DD 直流剩余电流检测装置标准

> 来源: `raw/漏电/IEC62955_2018.md`（157页，IEC 62955 Edition 1.0）
> PDF 使用标准字体编码，pypdf 成功提取全文（343KB，约6600行），无需 OCR

#### 新增概念页
- ✨ **新增**: [[concepts/standard-iec-62955]] — IEC 62955:2018 RDC-DD 直流剩余电流检测装置标准
  - 全文编译：适用范围（Mode 3 充电，≤440V AC，≤125A，IΔdc=6mA）
  - 术语定义（RDC-DD/RDC-MD/RDC-PD/RDC-M-unit/RDC-M-module）
  - 分类体系（4.1.1 RDC-MD 三种子类型 + 4.1.2 RDC-PD 集成型）
  - 特性参数（Table 1-4：电压/分断时间/AC不动作时间/冲击耐受电压）
  - 构造要求（§8.1-8.15：材料/标志/防护/端子/PCB/电气间隙Table 6/温升Table 8）
  - 测试要求（§9.1-9.22：22项型式试验 + Table 9 清单 + Table 16 I²t/Ip + Table 17 功率因数）
  - EMC测试（环波200A + 浪涌3000A）
  - 可靠性测试（28次气候循环55°C/高湿 + 28周期40°C带载运行）
  - 电子元件老化（168h@40°C/1.1Un）
  - 附录A-O全部概要（测试序列A-J/短路分类/螺纹端子/例行试验/绝缘配合/铜铝兼容/专用工具/RDC-MD机械耦合Annex M/电气耦合Annex N/RDC-PD集成型Annex O）
  - 与IEC 61851-1、IEC 62752、GB 44263的关联分析

#### 更新实体页
- 📝 **更新**: [[entities/product-ac-charger-eu]] — 新增 IEC 62955:2018 适用标准、Mode 3 漏电保护引用
- 🔗 **链接**: [[concepts/standard-iec-62955]] ↔ [[concepts/standard-iec-61851-1]]（Mode 3 充电系统 → RDC-DD 漏电保护补充）
- 🔗 **链接**: [[concepts/standard-iec-62955]] ↔ [[concepts/standard-iec-62752]]（Mode 3 vs Mode 2 漏电保护互补）
- 🔗 **链接**: [[concepts/standard-iec-62955]] ↔ [[concepts/standard-gb-44263]]（国标 RCD 要求与 IEC 62955 参数一致）
- ⚠️ **矛盾标注**: IEC 61851-1:2017 仅要求 Type A RCD，而 IEC 62955:2018 要求 6mA 平滑 DC 检测（后者更严格）
- 📊 **索引更新**: 总页面数 23→24，概念页 9→10

## 2026-07-27

### Ingest: 全球插头插座标准 + 全球插头查询模块

> 来源: `raw/插头标准/多国插头及电压标准.md`（Excel，2个工作表：208国插头信息 + 15种插头型号说明）
> 使用 openpyxl 提取全文数据，输出至 `raw/_extracted/plug_types_worldwide.txt`（11.8KB）

#### 新增概念页
- ✨ **新增**: [[concepts/plug-types-worldwide]] — 全球插头插座型号体系（Type A–O）
  - 15种插头型号详解：形状、标准号、额定电流、主要地区、说明
  - E型 vs F型矛盾标注（接地方式不同，CEE 7/7混合插头兼容）
  - 电压频率体系（北美100-130V/60Hz vs 国际220-240V/50Hz）
  - 特殊频率国家（日本50/60Hz分区域、韩国60Hz、沙特60Hz）
  - 双电压国家标注（巴西/利比亚/摩洛哥等9国）
  - 与充电桩产品关联（按产品线匹配插头、IC-CPD随车充特殊要求、充电模式与插头关系）

#### 新增主题页
- ✨ **新增**: [[topics/global-plug-lookup]] — 全球插头查询模块（杰哥要求新增的核心模块）
  - 208个国家/地区按大洲分组完整查询表（东亚/东南亚/南亚/中亚/西亚/西欧/北欧/南欧/东欧/北美/中美加勒比/南美/北非/撒哈拉以南非洲/大洋洲）
  - 15种插头型号（A-O）反查表：每种型号的代表国家列表
  - 电压/频率体系汇总：北美体系 vs 国际体系 + 特殊频率国家 + 双电压国家
  - 充电桩产品出口参考表：10个目标市场的插头型号/电压频率/产品线/认证要求

#### 更新索引
- 📝 **更新**: [[index]] — 总页面数 24→26，概念页 10→11，主题页 2→3，新增按标准查询条目

#### 交叉引用建立
- 🔗 [[concepts/plug-types-worldwide]] ↔ [[topics/global-plug-lookup]]（概念详解 ↔ 查询入口）
- 🔗 [[concepts/plug-types-worldwide]] ↔ [[concepts/charging-modes]]（插头型号 ↔ 充电模式）
- 🔗 [[concepts/plug-types-worldwide]] ↔ [[concepts/standard-iec-62752]]（插头匹配 ↔ IC-CPD随车充）
- 🔗 [[topics/global-plug-lookup]] ↔ [[topics/certification-by-region]]（插头查询 ↔ 认证查询）
- 🔗 [[topics/global-plug-lookup]] ↔ [[entities/product-ac-charger-cn]]、[[entities/product-ac-charger-eu]]、[[entities/product-ac-charger-us]]

#### 关键编译内容
- 15种插头型号覆盖全球所有民用电源标准
- 208国数据按大洲分15组，支持正查（国家→插头）和反查（插头→国家）
- 充电桩出口参考：10个主要目标市场的插头/电压/频率/认证一览
- IC-CPD随车充特别提醒：必须匹配目标国民用插座插头型号

## 2026-07-23（续）

### 源文件格式迁移：PDF/OCR/Excel → Markdown

> 用户将 `raw/` 目录中所有原始资料从 PDF/OCR/Excel 格式全部替换为干净的 Markdown 格式，重新编译引用路径。

#### 源文件变更（8个文件，约29,600行）
- 📄 `raw/欧标/桩标准/IEC 61851-1-2017-1.md`（7084行）— 代替原 PDF（分为2个文件）
- 📄 `raw/欧标/桩标准/IEC 61851-1-2017-2.md`（2174行）— 第二部分
- 📄 `raw/欧标/随车充标准/IEC 62752 2024(1).md`（5617行）— 代替原 PDF + OCR 中间文件，不再依赖 OCR
- 📄 `raw/漏电/IEC62955_2018.md`（5229行）— 代替原 PDF
- 📄 `raw/国标/GB 39752-2024 电动汽车供电设备安全要求.md`（1311行）— 代替原 PDF
- 📄 `raw/国标/GB 44263-2024 电动汽车传导充电系统安全要求_unlocked.md`（908行）— 代替原 PDF
- 📄 `raw/国标/GB_T 18487.1-2023 电动汽车传导充电系统　第1部分：通用要求.md`（5051行）— 代替原 PDF
- 📄 `raw/插头标准/多国插头及电压标准.md`（2234行）— 代替原 Excel 文件

#### Wiki 页面批量更新（22个文件，102处路径替换）
- 📝 **批量更新**: 全部22个 wiki 文件中的 `[[raw/...]]` 源文件引用路径从旧的 PDF/OCR/Excel 路径更新为新的 Markdown 路径
- 📝 **描述更新**: "OCR提取全文编译" → "Markdown全文编译"、"XX页" → "XXXX行"等描述文本同步更新
- 🔧 **修复**: `standard-iec-62752.md` 和 `comparison-iec-61851-vs-62752.md` 中批量替换产生的重复引用（原 PDF 引用和 OCR 中间文件引用指向同一新文件），合并为单条引用
- 🗑️ **废弃**: IEC 62752 不再需要 OCR 中间文件（`raw/_extracted/IEC_62752_ocr.txt`），用户提供的干净 Markdown 直接作为源文件

#### 涉及的 wiki 文件清单
log.md, index.md, charging-modes.md, comparison-gb-vs-iec-safety.md, comparison-iec-61851-vs-62752.md, plug-types-worldwide.md, safety-tests-iec-61851.md, standard-gb-39752.md, standard-gb-44263.md, standard-gb-t-18487-1.md, standard-iec-61851-1.md, standard-iec-62752.md, standard-iec-62955.md, certification-cb.md, certification-ccc.md, certification-ce.md, certification-cqc.md, product-ac-charger-cn.md, product-ac-charger-eu.md, region-china.md, region-europe.md, certification-process-overview.md, global-plug-lookup.md

### 当前状态
- ✅ 源文件格式统一为 Markdown，不再依赖 PDF/OCR/Excel 中间产物
- ✅ 全部 wiki 页面引用路径已同步更新
- ⏳ 待执行: MkDocs 构建并推送到 GitHub Pages

## 2026-07-29（续二）

### 完整性危机与架构升级：新增"原始标准全文"板块

> 用户反馈：在 GB/T 18487.1-2023 源文件中能搜到"二极管存在性检测"，但部署站点搜不到。
> 根因核查：wiki 页面为"提炼摘要"，相对源文件标题覆盖率仅 5%~28%（iec-61851-1 5.1%、gb-t-18487-1 6.2%、iec-62752 11.1%、iec-62955 17.9%、gb-39752 18.5%、gb-44263 28.2%），源文件大量章节（附录/测试程序/控制导引电路细节）未进 wiki，搜索只索引 wiki 页故搜不到。

#### 修复措施
- 🐛 **补全**: [[concepts/standard-gb-t-18487-1]] 新增"控制导引电路与二极管检测"章节——附录A.2.6二极管存在性检测、附录C防反灌二极管（D1定义/启动电流限制C.7.5/绝缘阻抗C.7.8.1/§11开关部件防护）、二极管压降Vd1
- 📚 **新增板块**: `wiki/standards/` 目录复制 8 份原始标准 Markdown 全文，加进 mkdocs.yml 导航"原始标准全文"
- 🔗 **链接修复**: 22个 wiki 文件 82 处 `[[raw/...]]` 来源链接改为指向 `[[standards/...|全文]]`，点"来源"直达标准全文（此前为断链）
- 🔍 **搜索保证**: 8份全文加入站点搜索索引，任何术语（含"二极管"）均可在站内搜到
- 📝 **索引更新**: [[index]] 新增"原始标准全文"板块入口

#### 待后续
- standards/ 为 raw/ 的副本，用户更新 raw/ 后需在部署前重新同步（可脚本化）
- 图表类标准（IEC 62196 接口、GB/T 20234）尚未编译，待资料

### 当前状态
- ✅ 完整性危机已缓解：wiki 摘要 + 原始全文双轨，搜索覆盖 100% 源内容
- ✅ GB/T 18487.1 二极管内容已补全
- ✅ 已构建并部署至新账号 jjjjjjxia 的 GitHub Pages

## 2026-07-30 — 全量完整性核查 + 英文标准翻译校对

> 用户要求：确认全量文件已上传、每个字可快速检索、英文 IEC 标准翻译校对万无一失。

### 核查结论
- ✅ **全量上传**：8 份 raw 源文件 → 8 份 `wiki/standards/` 副本，内容 100% 一致；已重新同步为字节级一致（MD5 全 MATCH）；全部进入导航、构建产物与线上 gh-pages 分支
- ✅ **可检索性**：搜索索引 3352 文档（standards 全文页 2683 个，按章节粒度切分）；中文（二极管/充电/剩余电流/控制导引）与英文（diode/RDC-DD/IC-CPD/Type 2/Mode 3/inrush current）术语均命中

### 翻译校对修正（3 份英文 IEC 标准，均经原文二次确证）
- 🐛 [[concepts/standard-iec-62752]]（Edition 2, 2024）:
  - Table 6 电缆截面积 `20A<I≤32A` 由 **4.0→6 mm²**（原文 L1906 明确为 6）
  - 型式试验项数 **36→34 项**（Table 9 条款 9.3–9.36）
  - 补充 UK/IE（BS 1363-1，≤13A）插头温度监控装置豁免（NOTE 3）
  - 补充 IAno 在 4.4.2 型且 IAn=30mA 时可降至 0.25×IAn（L1457）
- 🐛 [[concepts/standard-iec-62955]]（2018）:
  - Table 9 型式试验项数 **22→20 项**
  - 额定短路通断电流 Im 公式 **min→max**（取较大值，原文 L895 "whichever is the greater"）
  - Table 2 平滑直流分断时间去除错误倍数标注（6/60/200mA 为绝对值，非 2×/4×IΔdc）
  - §9.18.1 删除误标的 "8/20μs 波形前半周期"（该波形属 §9.18.2 浪涌）
  - 删除无依据的 "≥0.08s 选择性" 要求
  - 补充 Annex K（免螺钉端子）/L（端子示例）
- 📝 [[concepts/charging-modes]] / [[concepts/standard-iec-61851-1]]: 控制导引(CP)章节补全经原文核实参数（±12V 电平 State A/B/E、1kHz±0.5%、占空比 10%–96%、状态机）

### 待后续
- 用户更新 raw/ 后，部署前需重新同步 `wiki/standards/`（可脚本化）
- 图表类标准（IEC 62196 接口、GB/T 20234）尚未编译，待资料
- 中→英跨语言搜索（如中文"二极管"命中英文 "diode" 全文）仍依赖中文 wiki 页，可在全文页加双语术语表进一步强化
