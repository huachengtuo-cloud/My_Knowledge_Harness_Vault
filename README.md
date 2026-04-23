# 🌌 原点分化双轨映射系统 & LLM Wiki (Harness Edition)

> **核心哲学**：同源双轨，基底分化。将 Obsidian 视作 IDE，将知识库视作由 AI 托管的代码库。

---

## 1. 核心理念 (Core Philosophy)

本系统通过“物理隔离、逻辑融合”的架构，解决信息囤积与行动瘫痪的问题。

* **同源双轨**：个人知识库 (PKB) 与任务管理系统 (TMS) 共享底层文件骨架，通过属性（Metadata）和视图（Dataview）在逻辑层实现“静”与“动”的分离。
* **基底分化**：所有外部信息统一进入“原点”。经由“强制决策（Inbox Zero）”，分化为**长期生长的知识**（流入 Wiki）或**线性执行的任务**（流入 Action）。
* **AI 托管编译**：利用 LLM 作为“知识程序员”，负责对原始资料进行自动化总结、建立双链、维护索引和术语表。

---

## 2. 目录架构 (Directory Structure)

### 00_Inbox_原点 (The Origin)
全系统唯一的信息物理入口，遵循 **Inbox Zero** 原则。
- `01_RawMaterials_原始素材`: 存放待处理的网页剪藏、长文档、SkipClass 自动转写稿。
- `02_InitialIdeas_初期想法`: 存放主观灵感与即时闪念。
- `03_Notepad_记事本`: 记录人、事、物及精彩瞬间。

### 01_Materials_参考底座 (The Base)
静态输入区，不建立全局索引，仅作客观资料备查。
- `01_TechDocs_技术文档`: 官方 API、框架手册、代码示例。
- `02_Standards_标准规范`: 国家标准、法律规章。
- `03_LifeRef_生活参考`: 菜谱、装修、家庭经营资料。

### 02_Wiki_知识网络 (The Network)
动态生长区，存放经分化提纯后的主观认知。
- `00_Index_全局索引.md`: **大脑中枢**。AI 维护的逻辑导航地图。
- `00_Glossary_术语表.md`: **概念锚点**。跨领域的术语定义一致性维护。
- `00_Log_操作日志.md`: **审计追踪**。记录 AI 对库执行的编译与修改行为。
- `01_Tech_软件开发`: AI Agent 架构、Java/React 脚手架、Harness 工程心得。
- `02_Health_身心健康`: 八段锦、五行理论、身体调理体悟。
- `03_Business_商业运营`: 承拓百货运营 SOP、自媒体文案逻辑。
- `04_Growth_个人成长`: 4FS 系统迭代、学习方法论。

### 03_Action_执行空间 (The Space)
线性推进区，存放分化出的行动指令。
- `00_行动中枢_Dashboard.md`: 任务聚合看板。
- `01_Goals_目标`: 长期宏观愿景。
- `02_Plans_规划`: 中期实施路径。
- `03_Schedules_计划`: 短期具体排期。
- `04_Tasks_任务`: 原子级执行动作（- [ ]）。

### 04_Output_最终产出 (The Outputs)
系统流动性的终点，对外交付的成果归档。
- `01_Media_自媒体发布` | `02_Courses_线上课程` | `03_Projects_项目交付`

### 99_System_基础服务 (The Infrastructure)
- `01_Templates`: 知识与任务模板。
- `02_Prompts`: AI 指令集（如：无界010号成员）。
- `04_Assets`: 统一存放图片、附件。

---

## 3. 运行指南 (Operation Guide)

### A. 捕获与分化流 (Capture-to-Action)
1.  **输入**：任何资料先扔进 `00_Inbox_原点`。
2.  **决策**：
    - 是**客观事实/参考资料**？ -> 移入 `01_Materials_参考底座`。
    - 是**知识节点/体悟**？ -> 应用知识模板，移入 `02_Wiki_知识网络`。
    - 是**行动待办**？ -> 提取任务标签 `#实践任务`，移入 `03_Action_执行空间`。

### B. AI 协作指令 (LLM Commands)
通过 `Claudian` 或 `Claude Code` 插件执行：
- `/ingest [文件路径]`: 触发 AI 编译。AI 会通读原点文件，更新 Wiki 下的相关页面、Index、Glossary 并记录 Log。
- `/query [问题]`: AI 会优先检索 `02_Wiki` 的认知，结合底层 `01_Materials` 给出回答。

### C. 边界与隔离 (Isolation Rules)
- **代码隔离**: 工程项目（Git、依赖包）绝对不进入本仓库。
- **环境隔离**: Python 环境使用 `.venv`，AI 脚本使用 `.claude/skills`，保持仓库纯净。

---

## 4. 核心元文件维护规范

1.  **Index**: 必须体现知识的层级与交叉引用，而非简单的文件列表。
2.  **Glossary**: 词条必须具有“单一事实来源”，避免在多处笔记中重复定义。
3.  **Log**: 格式为 `| 日期 | 操作 | 源文件 | 影响节点 |`。