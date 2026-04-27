# Hive - The System of Record for Enterprise Agents

> Enterprise Agent Asset Infrastructure.
>
> Employees leave. Agents should not.
>
> Hive makes agents company-owned, governed, and inheritable.

*文档版本：v1.4 VC-facing draft*

---

## 1. Executive Summary

Hive 是企业级 Agent 资产中台。

企业已经开始让 AI Agent 进入真实业务：客服回复、销售跟进、市场内容、数据检索、会议纪要、流程触发、文档处理。但绝大多数 Agent 仍然依附于个人账号、单一 SaaS、一次性任务或工程项目。它们可以帮员工完成工作，却没有成为公司真正可继承、可治理、可审计的资产。

Hive 解决的是 Agent 时代的组织所有权问题：

- **Who they are**：Agent 的身份、角色、目标和工作边界沉淀在 `soul.md`；
- **What they know**：对话、工具调用、工作结果进入 T0/T2/T3 长期记忆管线；
- **Who can access them**：用户、角色、部门、租户和资源级权限决定谁能查看、使用或管理 Agent；
- **What they can do**：所有工具调用经过 Security Zone、Capability Policy 和 Approval Flow；
- **Where they work**：通过飞书 / Lark、Slack、Discord、钉钉、企微、Teams 等企业通道进入真实工作场景；
- **How they are inherited**：员工离职、转岗或组织调整时，Agent 和它的记忆、权限、流程状态留在公司。

一句话：**Hive is the system of record for enterprise agents.**

---

## 2. The Problem

### 2.1 Agent 能力不是最大瓶颈，组织归属才是

市场上的主流 Agent 产品正在快速解决“能不能做事”的问题：更强模型、更长上下文、更好工具调用、更自然的 Agent Builder。

但企业真正部署时，问题会从能力转向组织治理：

| 企业问题 | 传统 Agent / Copilot 的缺口 |
|---|---|
| Agent 的长期记忆归谁？ | 往往跟随个人账号、聊天窗口或单一 SaaS |
| 员工离职后 Agent 怎么交接？ | 没有稳定的身份、记忆和工作状态继承机制 |
| 谁能查看、使用、管理这个 Agent？ | 常被简化成个人账号权限，难以映射真实组织结构 |
| Agent 能调用哪些工具？ | 权限常和 SaaS 账号绑定，缺少跨工具治理层 |
| Agent 做过什么，为什么这么做？ | 审计、审批、上下文回放不完整 |
| 新负责人如何接手历史判断？ | Wiki/SOP 能交接流程，但很难交接真实决策口径 |

这不是“再做一个 Agent Builder”的问题，而是企业需要一个 Agent 生命周期系统：创建、授权、工作、记忆、审计、交接、演化。

### 2.2 “一人部门”是最清晰的切入场景

AI 不会立刻创造“一人公司”，但会快速创造“一人部门”：一个负责人带一组 Agent 执行客服、市场、销售运营、招聘协调、财务助理等域内工作。

一人部门提高效率，也放大了组织风险：

- 负责人离开，公司失去的不只是人力；
- 更严重的是，Agent 的上下文、工作口径、客户状态、工具组合和隐性判断一起流失；
- 传统团队可以靠人员冗余传承经验，一人部门没有这个缓冲层。

Hive 的切入点是：**让一人部门的 Agent 从第一天起就是公司资产，而不是个人外挂。**

---

## 3. Product

### 3.1 Hive 把 Agent 变成公司资产

Hive 的核心闭环不是一次性创建，而是持续循环：

| 阶段 | 动作 | 公司沉淀的资产 |
|---|---|---|
| 1. Hire | HR Agent 通过对话创建数字员工 | 初始岗位目标、职责、协作风格 |
| 2. Identity | 生成 `soul.md` | 角色、边界、决策口径 |
| 3. Work | 接入飞书 / Slack / Teams / 企微等通道 | 进入真实工作流 |
| 4. Act | Agent 调用工具、处理任务、触发流程 | 工具链、任务状态、工作结果 |
| 5. Learn | T0 → T2 → T3 → `soul.md` | 长期记忆和演化后的判断方式 |
| 6. Govern | 权限策略、审批和审计持续约束 | 可追溯的操作边界 |
| 7. Inherit | 员工离职或转岗 | Agent、记忆、流程、权限状态留在公司 |

这条闭环让 Agent 不只是聊天助手，而是可管理的“数字员工资产”。

### 3.2 六个产品支柱

| 支柱 | Hive 做什么 | 对企业的价值 |
|---|---|---|
| Persistent Identity | `soul.md` 记录 Agent 的角色、风格、目标和边界 | Agent 有稳定身份，不因单次会话清零 |
| Long-term Memory | T0/T2/T3 记忆管线和 Dream/Heartbeat 整理 | 真实工作中的判断逐步沉淀 |
| Enterprise Permission Control | 用户、角色、部门、租户、资源级权限共同决定谁能查看、使用、管理 Agent | Agent 能进入真实组织结构，而不是停留在个人账号里 |
| Tool Governance | Security Zone、Capability Policy、Approval Flow | 企业敢把 Agent 接入邮件、文档、IM、业务系统 |
| Channel-native Work | 多 IM 通道和企业工具集成 | Agent 在员工已有工作流中被使用 |
| HR Agent Onboarding | 通过对话创建数字员工 | 降低部署门槛，从 IT 项目变成员工自助 |

### 3.3 权限控制是独立基础层

Hive 的权限不是单点开关，而是两层控制面：

| 控制面 | 解决的问题 | 典型能力 |
|---|---|---|
| Human → Agent | 谁能查看、使用、管理、交接某个 Agent | platform admin / org admin / creator / company / department / user / resource permission |
| Agent → Tool / Data | Agent 能调用哪些工具、访问哪些外部系统、哪些动作需要审批 | Security Zone、Capability Policy、Guard Policy、Approval Flow、Audit Log |

这层权限控制决定 Hive 能否进入企业生产环境。没有它，Agent 只能是个人效率工具；有了它，Agent 才能成为可部署、可授权、可审计、可交接的公司资产。

---

## 4. Why Hive Is Different

### 4.1 不是更强的聊天助手，而是 Agent 的资产账本

企业不会缺 Agent。企业会缺一个地方来回答这些问题：

- 这个 Agent 是谁创建的？
- 它代表哪个岗位、部门和权限边界？
- 它知道哪些历史背景？
- 它调用过哪些工具？
- 哪些动作被拒绝、审批或审计？
- 负责人换人后，新负责人如何继承？

Hive 的定位不是替代所有 Agent，而是成为企业 Agent 的资产层和治理层。

### 4.2 竞争定位

| 类型 | 代表产品 | 优势 | Hive 的差异 |
|---|---|---|---|
| 企业套件内 Agent | Microsoft Copilot Studio、Salesforce Agentforce | 绑定现有企业数据和工作流，销售渠道强 | Hive 跨平台，不被单一 SaaS 数据边界限制；以 Agent 资产继承为第一原则 |
| 企业搜索 / 工作 AI | Glean Agents | 连接企业知识源，治理和搜索能力强 | Hive 更强调 Agent 身份、长期工作记忆、工具审批和离职交接 |
| 开源 Agent 框架 | LangChain、AutoGen、CrewAI | 开发者生态强，灵活 | Hive 面向组织部署，内置租户、权限、审批、通道和记忆生命周期 |
| 垂直 Agent | Devin、Cursor、Sierra 等 | 单场景能力深 | Hive 是承载多个岗位 Agent 的公司中台 |
| 个人 Agent / 通用助手 | Manus、OpenClaw、ChatGPT Agent 等 | 个人体验和通用能力强 | Hive 关注 Agent 归属公司、可审计、可交接 |

关键判断：Microsoft、Salesforce、Glean 的出现不是威胁叙事，而是市场验证。它们证明企业 Agent 已经进入预算周期。Hive 要占据的缺口是：**独立、跨平台、以公司资产继承为核心的 Agent lifecycle layer。**

---

## 5. Product Evidence

以下是当前仓库中已经可以核验的产品基础，不是远期概念。

### 5.1 已实现的工程资产

| 能力 | 当前证据 |
|---|---|
| Agent Kernel | `backend/app/kernel/engine.py`，统一处理 WebSocket、通道、Trigger、Heartbeat、Delegation 等路径 |
| 4 层记忆 | `backend/app/services/memory_service.py`、`backend/app/services/auto_dream.py`、`backend/app/services/heartbeat.py` |
| `soul.md` 身份契约 | Kernel、agent context、auto dream 均读取或更新 `soul.md` |
| Enterprise Permission Control | `backend/app/core/permissions.py`、`backend/app/models/agent.py` 中的 `AgentPermission`、`backend/app/models/security_audit.py` 中的 `ResourcePermission` |
| Tool Governance | `backend/app/tools/governance.py`、`backend/app/services/capability_gate.py`、`backend/app/models/capability_policy.py` |
| Approval Flow | `backend/app/models/audit.py` 中的 `ApprovalRequest`，以及 runtime/tool governance 测试 |
| Guard Policy | `backend/app/models/guard_policy.py` 支持租户级 zone / egress guard 策略 |
| 多租户基础 | `tenant_id` 贯穿核心模型，核心表已有 RLS migration，LLM、工具、通道配置按租户隔离 |
| 企业通道 | Feishu/Lark、Slack、Discord、DingTalk、WeCom、Teams API 或 runtime 模块 |
| HR Agent 创建 | `create_digital_employee` 工具和 HR Agent endpoint 测试 |
| 测试基础 | 当前仓库约 191 个 backend test 文件、17 个 frontend test 文件 |

### 5.2 当前阶段判断

Hive 已经不是 PPT 概念。它具备一个 Agent 资产中台的底层骨架：

- 身份层：Agent 有持久人格和岗位契约；
- 记忆层：工作过程能沉淀成长期记忆；
- 权限层：用户、部门、租户、资源和 Agent 工具能力都能被分层控制；
- 审批层：高风险工具调用可被策略和审批拦截；
- 通道层：Agent 能进入企业已有沟通场景；
- 租户层：公司级隔离和配置已经进入架构。

下一阶段重点不应是继续堆通用能力，而是把这些能力压成 2-3 个可付费的一人部门样板。

---

## 6. Wedge: One-person Departments

Hive 最适合从高频、可衡量、可复用的“一人部门”切入。

### 6.1 首批样板

| 样板部门 | Agent 工作内容 | ROI 衡量 |
|---|---|---|
| 客服主理 | 客户问题分流、历史记录检索、回复草拟、升级判断、售后跟进 | 响应时间、一次解决率、人力节省、升级准确率 |
| 市场内容主理 | 选题、竞品监控、素材整理、内容初稿、渠道排期 | 内容产量、发布时间、复用率、转化线索 |
| 商务 / 销售运营 | 客户跟进、会议纪要、报价材料、合同节点提醒、CRM 更新 | 跟进及时率、丢单减少、销售行政时间下降 |

### 6.2 试点交付方式

每个试点客户不卖“平台大而全”，只交付一个可跑通的部门闭环：

- 1 个负责人；
- 2-5 个部门 Agent；
- 1 套 soul 模板；
- 1 套 skill pack；
- 3-5 个 trigger 配方；
- IM 通道接入；
- 审批和审计策略；
- 30 天 ROI 看板。

试点成功的关键不是“Agent 回答得多聪明”，而是完成一次可验证的组织交接测试：

> 把负责人换成另一个人，新负责人是否能通过 Hive Agent 理解历史客户、工作口径、当前任务和权限边界，并继续推进工作。

这会成为 Hive 最强的销售材料。

---

## 7. Business Model

Hive 的收入结构应当围绕“企业 Agent 资产中台”设计，而不是单纯围绕 token 转售。

### 7.1 三层收入

| 收入层 | 计费方式 | 价值来源 |
|---|---|---|
| Enterprise License | 按公司 / 部门 / 私有化部署年付 | 多租户、权限、审计、SSO、合规、管理后台 |
| Usage Credits | 按模型调用、工具调用、后台任务和自动触发消耗 | Agent 工作越多，客户价值和平台收入同步增长 |
| Workflow Packs | 按部门模板、行业 pack、premium 工具和深度集成收费 | 把成功样板产品化，提升毛利和复用率 |

Usage Credits 是用量型价值捕获：客户为 Agent 完成的工作、节省的人力和保留下来的组织记忆付费。

### 7.2 为什么不是纯 seat 模式

| Seat 模式 | Hive usage + license 模式 |
|---|---|
| 收入受员工数限制 | 收入随 Agent 工作量和自动化深度增长 |
| 每增加 Agent 都可能触发采购摩擦 | 钱包 / credits 可承接持续消耗 |
| 与 Agent 主动性弱相关 | Trigger、Heartbeat、Dream、Delegation 都能转化为可计量价值 |
| 容易被当成又一个 SaaS seat | 更接近云资源 + 工作流自动化 + 治理中台 |

---

## 8. Why Now

### 8.1 企业 Agent 已进入预算周期

Microsoft Copilot Studio、Salesforce Agentforce、Glean Agents 等产品已经把 enterprise agents、governance、agent builder、usage-based pricing 带入企业采购讨论。这说明品类正在被教育，预算正在形成。

Hive 不需要证明“企业会不会买 Agent”。Hive 要证明的是：**当企业真的部署大量 Agent 后，需要一个独立资产层管理它们。**

### 8.2 组织正在从“人用 AI”走向“人管理 Agent”

第一阶段是 Copilot：员工让 AI 帮自己写、查、总结。

第二阶段是 Agent：员工把一部分流程交给 AI 自动执行。

第三阶段是 Agent Organization：公司需要管理这些 Agent 的身份、权限、记忆、审计和交接。

Hive 面向第三阶段。

### 8.3 合规和审计会从加分项变成准入条件

AI Act 等监管趋势强调透明度、风险分类、问责和高风险系统要求。不是所有企业 Agent 都会被归为高风险系统，但企业客户会越来越要求：

- 操作可追溯；
- 权限可解释；
- 高风险动作可审批；
- 数据边界可证明；
- Agent 输出和工具调用可审计。

这正好对应 Hive 的底层架构。

---

## 9. Roadmap

### 0-6 个月：把一人部门做成可复制样板

目标：

- 完成 3 个付费或强绑定 design partners；
- 跑通客服主理、市场内容主理、商务 / 销售运营 3 个部门模板；
- 每个模板沉淀 soul 模板、skill pack、trigger 配方、审批策略和 ROI 看板；
- 完成至少 1 次“负责人交接测试”案例。

核心指标：

- 每个 Agent 每周处理的真实工作项；
- 自动触发任务数；
- 人工审批通过率 / 拒绝率；
- 负责人节省时间；
- 新负责人接手所需时间；
- 客户愿意为部门 pack 付费的价格。

### 6-18 个月：从样板到中台

目标：

- 将成功样板打包为 Workflow Packs；
- 建立 Agent 模板、skill pack、trigger recipe 的复用体系；
- 加强私有化部署、SSO、审计报表、企业权限矩阵；
- 扩展行业集成：CRM、ERP、HRIS、客服系统、文档系统。

核心指标：

- Pack 复用率；
- 每客户 Agent 数；
- 每客户 usage credits 消耗；
- 部门级扩张率；
- NRR（Net Revenue Retention，净收入留存率）。

### 18-36 个月：成为企业 Agent 的系统记录层

目标：

- 成为公司内部所有 Agent 的 registry、memory、policy 和 audit layer；
- 支持跨部门 Agent 协作和组织级 Agent 拓扑；
- 建立第三方 pack / plugin 生态；
- 进入中大型企业私有化和行业方案市场。

---

## 10. Fundraising Use of Funds

本轮融资应围绕“把技术骨架变成可销售样板”使用。

建议资金用途：

| 用途 | 占比 | 目标 |
|---|---:|---|
| 产品工程 | 40% | 强化 Agent lifecycle、记忆可视化、审批审计、ROI 看板 |
| 试点交付 | 30% | 做深 3 个一人部门样板，形成可复用交付手册 |
| 安全与企业化 | 20% | SSO、私有化部署、权限矩阵、审计导出、数据隔离验证 |
| 开源与生态 | 10% | 开源社区、skill pack、开发者文档、早期合作伙伴 |

对投资人的阶段承诺不应是“我们会做一个大平台”，而是：

> 6 个月内证明：一个部门负责人离开后，公司仍然能通过 Hive Agent 继承他的上下文、判断口径和关键工作流。

---

## 11. Investor Takeaway

Agent 时代的企业软件，不会只是谁的模型更强，也不会只是谁的 Agent Builder 更好用。

真正稀缺的是企业能否拥有自己的 Agent 资产：

- Agent 的身份归公司；
- Agent 的记忆归公司；
- Agent 的权限由公司治理；
- Agent 的行为被公司审计；
- Agent 的工作状态可以被下一个负责人继承。

Hive 要做的不是另一个 Copilot，而是企业 Agent 的资产基础设施。

> Employees leave. Agents should not.
>
> Hive makes agents company-owned, governed, and inheritable.

---

## 12. External References

以下外部信息用于校准市场位置，不作为 Hive 已实现能力声明：

- Microsoft Copilot Studio：企业可用自然语言或图形界面创建、测试、发布 agents，并支持组织治理、安全和 usage-based pricing。  
  https://www.microsoft.com/en-us/microsoft-365-copilot/microsoft-copilot-studio

- Salesforce Agentforce：Salesforce 将其定位为 enterprise agentic AI platform，强调企业级构建、测试、部署、管理和编排 AI agents。  
  https://www.salesforce.com/agentforce/

- Glean Agents：Glean 宣布 horizontal enterprise agent environment，强调企业数据连接、governance、agent builder 和多数据源。  
  https://www.glean.com/press/glean-makes-horizontal-ai-agents-for-enterprises-expands-work-ai-with-glean-agents

- EU AI Act：欧盟 AI Act 强调基于风险分类的透明度、问责和高风险系统要求。  
  https://www.consilium.europa.eu/en/press/press-releases/2024/05/21/artificial-intelligence-ai-act-council-gives-final-green-light-to-the-first-worldwide-rules-on-ai/
