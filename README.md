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

---

## 📈 自动化研究：Skill 自动上架
目前正在研究将商家繁琐的录入工作抽象为 **AI Skills**。
- **已实现：** 自动提取入库单图片信息、自动分类、自动生成营销文案。
- **技术栈：** Trae + FastAPI + Dify。

---

## 🔗 联系方式
- **Email:** 1312513223@qq.com
- **GitHub:** [https://github.com/whjwjx](https://https://github.com/whjwjx)
