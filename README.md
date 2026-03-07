# AI-Native Developer Showcase

本仓库用于展示我在开发过程中与 AI（Trae, OpenCode, Claude）深度协同的实战成果、效能数据及工程规范。

> **安全声明：** 本仓库所有截图及代码均已进行脱敏处理，不包含任何商业机密及私有业务逻辑。

---

## 🚀 AI 协同效能概览

### 1. 开发效率提升
- **核心功能交付：** 通过 AI 辅助重构与逻辑拆解，平均交付周期缩短约 **40%**。
- **代码生成比：** 在新功能开发中，AI 生成代码占比约 **60%-70%**，人工主要负责核心架构设计与逻辑 Review。

### 2. 编程报告示例
- [查看项目提交记录展示](screenshots/commits/cnb.md)
- [查看 Trae 使用统计报告](screenshots/ai_chats/AICoding.md)

---

## 🛠 AI 协同实战展示

### 1. 复杂逻辑拆解 (Trae Builder Mode)
**场景：** 自动化商品上架 Skill 开发
- **AI 角色：** 辅助设计 Function Calling 链路。
- **协同过程：** 
  1. 通过 Trae Builder 模式定义 Skill 接口规范。
  2. AI 自动生成多模态 OCR 识别逻辑。
  3. 人工接入企业级私有 API 鉴权。
- **截图：** `screenshots/ai_chats/skill_auto_listing_logic.png`

### 2. 原子化提交规范 (Atomic Commits)
**规范：** 遵循 Conventional Commits，每个 Commit 仅包含一个逻辑原子。
- **展示：** 即使在 AI 高频产出下，依然保持清晰的提交历史。
- **截图：** `screenshots/commits/atomic_commit_history.png`

### 3. Dify 智能导购助手优化 (Workflow 架构)
针对响应慢、幻觉乱编、回复死板等痛点，将架构从 Agent 模式升级为 **意图驱动的工作流 (Workflow)**。
- **极速响应**：引入“并行抢跑”机制，意图识别与 API 查询同步执行，响应延迟从 10s+ 降至 2-3s。
- **零幻觉保障**：通过专用 API 替代 SQL 自由写，结合“硬性约束指令”，确保回复数据 100% 对应接口字段。
- **智能分流**：内置意图分类器，实现“闲聊”与“搜索”路径的精准切换，兼顾拟人化体验与业务严谨性。
- **展示：**
  - ![Dify 工作流架构](screenshots/commits/image.png)
  - ![异步并行优化](screenshots/commits/image-2.png)

### 4. AI 全栈实战：StepOne — AI 驱动的个人效率管理平台 (核心展示)
**StepOne** 是一款融合了“类 Flomo 笔记”与“象限清单”的个人效率工具，旨在通过 AI 技术降低用户拆解复杂任务的认知成本。

- **项目官网**：[👉 stepone.huajiang.wang](https://stepone.huajiang.wang) (推荐访问)
- **项目角色**：全栈开发 (React + FastAPI)
- **核心技术**：React 18, Vite, Tailwind CSS 4, FastAPI, PostgreSQL, ModelScope (LLM), Docker, WebSocket
- **技术亮点与 AI 协同**：
  - **AI 任务智能化拆解**：集成 ModelScope (LLM) 接口，实现任务一键自动拆解为可执行步骤，通过 Prompt Engineering 优化大模型输出的结构化程度与逻辑性。
  - **高安全性会话管理**：基于 JWT + 设备指纹设计多端登录方案。支持 WebSocket 实时通信、主设备提权 (Master Device Elevation) 及远程强制下线，增强账号安全性。
  - **高性能前端架构**：利用 Radix UI 与 Tailwind CSS 4 构建响应式组件库；采用 Context API + Custom Hooks 优化全局状态管理，通过 DataProvider 作用域限制实现非必要请求的按需加载。
  - **稳健的后端工程化**：基于 FastAPI 异步框架构建 RESTful API，使用 SQLAlchemy + Alembic 管理数据库迁移，并采用 OpenAPI (Swagger) 契约优先模式，确保前后端接口高度对齐。
  - **敏捷开发与部署**：通过 Docker Compose 实现容器化一键部署；制定了“一事一档”任务追踪机制与标准的运维交付清单 (Ops Checklist)，具备完整的全栈项目全生命周期管理经验。
- **展示：**
  - ![StepOne 项目展示](screenshots/commits/stepone-github-page.png)

---

## 📈 自动化研究：AI 驱动的商品自动上架系统 (Smart Listing Agent)
针对多来源商家入库单格式混乱、图片提取难、人工录入效率低等痛点，通过 **AI Agent** 模式实现从原始 Excel 到上架完成的 **6 步全链路自动化**。

- **AI 智能交互与推理 (核心特色)**：
  - **自然语言驱动**：用户只需通过自然语言下达指令，如：“按照 6 步上架流程，帮我对 XXX 的入库单进行商品入库并上架”。
  - **自主 Skill 检索与编排**：AI 模型具备自主思考能力，能够根据用户意图自动检索并一步步调用底层 Skills，实现任务的闭环执行。
  - **异构 Excel 智能解析**：攻克了 AI 识别商品上架 API 所需字段参数的难题。AI 能自主处理各种复杂的 Excel 表结构，精准提取并映射参数，为后续自动化步骤提供高质量数据支撑。

- **核心亮点与技术攻关**：
  - **智能字段映射 (Smart Mapping)**：利用 `difflib` 模糊匹配算法实现表头识别，结合置信度校验（Confidence Score），准确率 >95%。
  - **深度图片提取 (Deep Extraction)**：通过 `zipfile` 解析 **OpenXML** 底层结构，精准定位图片在单元格中的锚点 (Anchor)，确保商品行图片 100% 精准匹配。
  - **数据治理与标准化**：自动清洗规格单位，并根据文件名语义自动推荐内部分类 ID。
  - **高效分发与存储**：集成 OSS 实现图片自动上传、压缩及 URL 回填，通过 RESTful API 批量分发标准化数据。

- **项目展示**：
  - **文件结构与代码组织**：
    ![项目文件截图](img/image.png)

- **技术栈**：Python 3.x, Pandas, OpenPyXL, Pillow, Zipfile/XML, Requests (REST API), AI Agent Framework.
---

## 🔗 联系方式
- **Email:** whj_cj2020@163.com
- **GitHub:** [https://github.com/whjwjx](https://https://github.com/whjwjx)
