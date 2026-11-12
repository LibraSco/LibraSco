# 李欣 · Li Xin

大连海事大学 · 物联网工程 · 大三在读（2028 届）
GPA 3.76 / 5.0（专业排名 10/59，前 17%）

**把 LLM demo 做成能评测、能解释失败的服务。** 目前找 Agent / LLM 应用开发实习。

---

## 项目

### [Agentic RAG 技术文档问答](https://github.com/LibraSco/fastapi-docs-rag) · LangGraph + 混合检索

面向 FastAPI 中文文档的问答服务：先判断该不该答，再拆解多跳问题，回答带引用、逐条校验。

- **编排**：LangGraph 状态机串起改写、路由、检索、自检、生成、校验；按问题类型走单跳、多跳或直接拒答，重查和重生成都有次数上限，不会无限循环
- **检索**：向量召回 + BM25 关键词召回，rerank 精排；关键词问法在 BM25 置信度高时直接短路，检索约 6ms，向量链路约 0.9s
- **服务**：FastAPI 按节点推送执行进度，会话持久化、请求追踪；同一套检索逻辑通过 MCP 暴露给外部客户端
- **评测**：自建 50 题分层集（单跳、口语、多跳、域外），45 道域内题 44 道在前 5 条找到依据，42 道引用对得上来源，5 道域外题全部拒答；16 个离线测试覆盖关键分支

`Python` `LangGraph` `FastAPI` `Chroma` `BM25` `MCP` `pytest`

### 头条新闻后端 · 高并发读写与一致性

面向新闻资讯场景的后端服务：分类浏览、详情查看、新闻发布，每次写操作异步记录审计。

- **列表分页**：分类过滤与时间排序共用联合索引，游标分页，10 万条下 95% 请求 16ms 内返回，深翻页不变慢
- **缓存**：空值缓存、互斥锁、TTL 抖动分别覆盖穿透、击穿、雪崩；更新后先改库再删缓存，用版本号整体失效，热点读 95% 在 26ms 内完成
- **写入**：版本号乐观锁防并发覆盖；审计走 Redis Stream 异步，事件 ID 幂等、失败进死信，不拖慢发布
- **质量**：25 个 pytest 用例覆盖分页边界、缓存失效、参数校验与权限；读、写、混合三类 locust 压测验证并发更新不丢数据、审计不重不漏

`Python` `FastAPI` `SQLAlchemy` `MySQL` `Redis` `Redis Stream` `pytest` `locust`

---

## 技术栈

- **Agent**：LangGraph 状态机与条件路由、Function Calling、MCP 工具接入、多 Agent 协作、SSE 流式输出
- **RAG**：文档切分、Embedding、Chroma 向量召回、BM25 关键词召回、rerank 精排、查询改写、引用校验与拒答、hit@k / MRR 评测
- **后端**：Python、FastAPI 异步、SQLAlchemy 异步 ORM、MySQL 索引与游标分页、Redis 缓存与一致性、pytest、locust、Docker
- **AI 编程**：熟练使用 Copilot、Codex、Trae 等 AI 编程工具提效
- **基础**：数据结构与算法、计算机网络、操作系统

## 写作与社区

- CSDN 60+ 篇技术博客，累计阅读 2W+，覆盖算法、Agent 实践与异步编程
- Trae 校园大使，校内推广 AI 编程工具

## 联系

- CSDN：[blog.csdn.net/Libra_pro](https://blog.csdn.net/Libra_pro)
- GitHub：[github.com/LibraSco](https://github.com/LibraSco)
