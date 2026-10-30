# 李欣 · Li Xin

大连海事大学 物联网工程 · 大三在读
寻找 Agent / LLM 应用开发实习

我把 LLM demo 做成能评测、能解释失败的服务。目前在两个方向上做深：

---

## 正在做

### [AI 旅行规划助手](https://github.com/LibraSco/ai-travel-planner) · LangChain 多 Agent + 高德 MCP

输入城市、日期和偏好，输出一份含景点、天气、酒店、餐饮和预算的可编辑行程。

基于 HelloAgents 教程骨架，独立完成 LangChain 多 Agent 重构：4 个单一职责 Agent 串行编排、16 个高德 MCP 工具按 Agent 分组暴露、异步懒加载 + 首请求 single-flight。

`Python` `FastAPI` `LangChain` `MCP` `Vue3`

### [RAG 技术文档问答](https://github.com/LibraSco/fastapi-docs-rag) · 两阶段检索 + 50 题评测

面向 FastAPI 中文文档：向量召回 top20 → gte-rerank 精排 top5，回答带引用，资料不足时拒答。

自建 50 题分层集做 A/B/C 对照，hit@5 从 0.911 到 0.956、MRR 从 0.793 到 0.854；保留 q036 / q037 等失败样本，用评测决定下一步改什么。

`Python` `LangChain` `Chroma` `DashScope` `Streamlit`

> 两个项目正在参赛，源码暂未公开。上面的仓库只放 README、截图和指标；需要看实现可以约时间现场演示。

---

## 技术栈

- **Agent**：LangChain、Function Calling、MCP（stdio、工具转换）、多 Agent 编排
- **RAG**：切分、Embedding、向量检索、cross-encoder 精排、引用与拒答、hit@k / MRR 评测
- **后端**：Python、FastAPI、Pydantic、异步编程
- **前端**：Vue3 / TypeScript 基础、Streamlit
- **工具**：Git、Linux；了解 Docker / Compose

## 写作与社区

- CSDN 60+ 篇技术博客，累计阅读 2W+，覆盖算法、Agent 实践与异步编程
- Trae 校园大使，校内推广 AI 编程工具

## 联系

- CSDN：[blog.csdn.net/Libra_pro](https://blog.csdn.net/Libra_pro)
- GitHub：[github.com/LibraSco](https://github.com/LibraSco)
- 邮箱：[17870469120@139.com]
