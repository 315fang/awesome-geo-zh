# awesome-geo-zh · 生成式引擎优化中文资源精选

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](LICENSE)

> **English intro:** A curated list of resources on **Generative Engine Optimization (GEO)** for the **Chinese AI-search ecosystem** — Doubao, Tencent Yuanbao, Kimi, DeepSeek, Baidu Wenxin / Baidu AI Search, Qwen / Quark, Metaso, Zhipu ChatGLM and others. Existing awesome-GEO lists are mostly English-centric; this one collects papers by Chinese researchers or about Chinese engines, official vendor docs (crawlers, web-search APIs, citation behavior), Chinese webmaster platforms, standards, and neutral Chinese-language tutorials. Every link was checked to load at the time of writing (2026-11). Contributions welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).

本列表收录面向中文 AI 搜索生态（豆包、腾讯元宝、Kimi、DeepSeek、文心 / 百度 AI 搜索、千问 / 夸克、秘塔、智谱清言等）的 GEO 资源：论文、官方文档、爬虫资料、站长平台、技术标准、教程与工具。只收能打开、有实质内容、立场中立的条目；不收代运营广告、付费墙内容和盗版资料。

**标签说明：** 【论文】同行评审或预印本 · 【代码】论文官方代码 · 【数据集】 · 【官方】厂商 / 标准组织 / 政府的一手文档 · 【产品】产品入口 · 【工具】可直接使用的工具或开源项目 · 【标准】协议与规范 · 【法规】 · 【文章】教程与评论 · 【列表】其他资源列表

> 披露：维护者同时维护 OpenGEO（opengeo.page）。来自 OpenGEO 的条目已在描述末尾注明「（维护者项目）」，与其他条目适用同一收录标准。

## 目录

- [什么是 GEO](#什么是-geo)
- [学术论文](#学术论文)
- [国内 AI 搜索产品与官方说明](#国内-ai-搜索产品与官方说明)
- [国内 AI 爬虫与官方文档](#国内-ai-爬虫与官方文档)
- [站长平台与收录工具](#站长平台与收录工具)
- [技术标准与官方指南](#技术标准与官方指南)
- [国内法规](#国内法规)
- [中文 GEO 文章与教程](#中文-geo-文章与教程)
- [观测与测量工具](#观测与测量工具)
- [社区与相关列表](#社区与相关列表)
- [贡献](#贡献)
- [许可](#许可)

## 什么是 GEO

GEO（Generative Engine Optimization，生成式引擎优化）一词由 Aggarwal 等人在 2023 年提出（[arXiv:2311.09735](https://arxiv.org/abs/2311.09735)，KDD 2024 接收）。它研究的问题是：在「先检索网页、再由大模型生成答案并标注来源」的生成式引擎里，内容创作者怎样让自己的内容更容易被选为来源、被准确地呈现在回答中。论文提出了评测基准 GEO-bench 和一组内容改写策略，实验中补充引用来源、统计数据、引语等策略最多让来源可见度提升约 40%，而传统的关键词堆砌几乎没有帮助，且不同领域的最优策略并不相同。GEO 和 SEO 不是替代关系：生成式引擎的检索环节大多仍依赖搜索引擎的抓取和索引，所以能被抓取、能被收录仍是前提。

## 学术论文

### 奠基与通用研究

- [GEO: Generative Engine Optimization](https://arxiv.org/abs/2311.09735) 【论文】 — GEO 概念的原始论文（Aggarwal 等，KDD 2024），提出 GEO-bench 与 9 种内容优化策略。
- [GEO-optim/GEO](https://github.com/GEO-optim/GEO) 【代码】 — 原论文的官方代码仓库，附 GEO-bench 数据集与排行榜链接（Apache-2.0）。
- [C-SEO Bench: Does Conversational SEO Work?](https://arxiv.org/abs/2506.11097) 【论文】 — 多领域对话式 SEO 评测基准，检验现有内容改写方法是否真的有效（NeurIPS 2025 Datasets & Benchmarks）。
- [What Generative Search Engines Like and How to Optimize Web Content Cooperatively](https://arxiv.org/abs/2510.11438) 【论文】 — 从生成式引擎偏好中自动提取规则并用于内容改写（CMU，AutoGEO）。
- [Do GEO Gains Survive the Live Web? (LIVE-GEO)](https://arxiv.org/abs/2611.01126) 【论文】 — 把 GEO 改写后的页面真正发布到公网，检验多种 GEO 方法在真实引擎中的效果，评测方含 DeepSeek、Kimi、Qwen。

### 中文场景与中国学者研究

- [中文生成式引擎优化](https://www.jos.org.cn/1000-9825/7771.htm) 【论文】 — 李彤等（中国人民大学、清华大学），《软件学报》2026：构建中文 GEO 评测框架，在国内生成式平台上比较中英文 GEO 的差异。
- [What Do Chinese-Language Generative Search Engines Cite and Surface?](https://arxiv.org/abs/2607.15771) 【论文】 — 4 个国内主流平台、8 个 Web/App 界面、614 个问题的大规模引用实证研究，分析信源、实体曝光与跨界面一致性。
- [From Citation Selection to Citation Absorption](https://arxiv.org/abs/2604.25707) 【论文】 — 提出「引用选择 / 引用吸收」两阶段测量框架（中国独立研究者，数据集公开于 GEOLab）。
- [CC-GSEO-Bench](https://arxiv.org/abs/2509.05607) 【论文】 — 以内容为中心、衡量单篇来源文章对生成式答案影响力的基准（浙江大学等）。
- [Role-Augmented Intent-Driven Generative Search Engine Optimization (RAID)](https://arxiv.org/abs/2508.11158) 【论文】 — 在无法预知目标查询的前提下，通过推断检索意图来做 GEO（中国科学技术大学）。
- [IF-GEO: Conflict-Aware Instruction Fusion for Multi-Query GEO](https://arxiv.org/abs/2601.13938) 【论文】 — 面向多查询场景、兼顾跨查询稳定性的 GEO 方法（中国科学技术大学）。
- [Think Before Writing: Feature-Level Multi-Objective Optimization (FeatGEO)](https://arxiv.org/abs/2604.19113) 【论文】 — 在可解释的特征空间而非逐词改写层面做 GEO，平衡可见度与内容质量（南京信息工程大学）。
- [IntentGEO: Intent-aware GEO for Recommendation](https://arxiv.org/abs/2611.04225) 【论文】 — 研究用户意图变化对推荐类 GEO 效果的影响，并在豆包上做了验证。

### 数据集

- [GEOLab（原 geo-citation-lab）](https://github.com/yaojingang/GEOLab) 【数据集】 — 公开的中文 AI 引用数据集（12 个国内平台形态、21 万条原始记录）、实验报告与 GEO 论文导航。

## 国内 AI 搜索产品与官方说明

### 字节跳动 · 豆包

- [豆包](https://www.doubao.com/) 【产品】 — 字节跳动的 AI 助手，支持联网搜索。
- [火山方舟：联网搜索工具](https://docs.volcengine.com/docs/ark/web-search?lang=zh) 【官方】 — 豆包大模型调用联网搜索的开发文档，对比「豆包搜索 Custom 版」与「联网内容插件」两种检索工具。

### 腾讯 · 元宝

- [腾讯元宝](https://yuanbao.tencent.com/) 【产品】 — 腾讯的 AI 助手，联网搜索可检索公众号、视频号等腾讯生态信源。
- [元宝搜索](https://so.qq.com/) 【产品】 — 腾讯的 AI 搜索入口，提供 AI 模式与传统关键词搜索。
- [元宝搜索 API 产品概述（腾讯云）](https://cloud.tencent.com/document/product/1806/121794) 【官方】 — 说明元宝搜索的数据基础（全网公开资源 + 腾讯新闻、搜狗百科、企鹅号等）和「结果权威度等级」等字段。

### 月之暗面 · Kimi

- [Kimi](https://www.kimi.com/) 【产品】 — 月之暗面的 AI 助手，是否联网由模型自动判断。
- [Kimi 帮助中心：Agentic 搜索](https://www.kimi.com/help/features/search) 【官方】 — 官方说明来源按相关性、权威性、时效性筛选，回答附来源链接，并列出优先与过滤的信源类型。

### 深度求索 · DeepSeek

- [DeepSeek](https://www.deepseek.com/) 【产品】 — 深度求索官网与对话入口。
- [DeepSeek API 更新日志](https://api-docs.deepseek.com/zh-cn/updates) 【官方】 — 2026-10-17 条目说明网页端与 API 的搜索由自研搜索引擎支撑，并称会识别过滤「SEO 作弊、GEO 操纵和低质 AIGC」。

### 百度 · 文心 / 百度 AI 搜索

- [文心（原文心一言）](https://wenxin.baidu.com/) 【产品】 — 百度文心助手，yiyan.baidu.com 现已跳转至此。
- [百度 AI 搜索（百度智能云）](https://cloud.baidu.com/product/ai-search.html) 【官方】 — 百度面向大模型的检索服务，返回站点、标题、URL、原文片段，支持指定站点范围。

### 阿里巴巴 · 千问 / 夸克

- [千问](https://www.qianwen.com/) 【产品】 — 阿里的 AI 助手（原通义千问）。
- [夸克](https://www.quark.cn/) 【产品】 — 阿里旗下的 AI 应用，内置 AI 搜索。
- [阿里云百炼：大模型如何联网搜索](https://help.aliyun.com/zh/model-studio/web-search) 【官方】 — 千问模型联网搜索文档，含返回来源（enable_source）与角标引用（enable_citation）参数。

### 其他

- [秘塔 AI 搜索](https://metaso.cn/) 【产品】 — 秘塔科技的 AI 搜索引擎。
- [智谱清言](https://chatglm.cn/) 【产品】 — 智谱的 AI 助手，现定位为多 Agent 协作平台。
- [智谱开放平台：联网搜索](https://docs.bigmodel.cn/cn/guide/tools/web-search) 【官方】 — Web Search API 文档，说明整合智谱自研引擎与搜狗、夸克等第三方搜索。

## 国内 AI 爬虫与官方文档

> 截至 2026-11，国内厂商里我们只找到月之暗面（Kimi）和腾讯混元发布了专门的 AI 爬虫文档；豆包、DeepSeek、千问、文心未找到公开的爬虫说明。如有官方来源，欢迎 PR 补充。

- [关于 Bytespider（头条搜索站长平台）](https://zhanzhang.toutiao.com/docs/intro/26899) 【官方】 — 字节跳动 Bytespider 的 PC/Android/iOS UA 与 10 个 IP 段；文档把它写作头条搜索爬虫，未说明是否用于豆包或模型训练。
- [Baiduspider 常见问题解答](https://help.baidu.com/question?prod_id=99&class=476&id=2996) 【官方】 — 百度各产品使用的 UA 列表、反向 DNS 核验方法与 robots 写法。
- [轻松两步，教你快速识别百度蜘蛛](https://ziyuan.baidu.com/college/articleinfo?id=3378) 【官方】 — 百度搜索资源平台的 UA 识别教程，含 Baiduspider-render。
- [腾讯混元 HySpider](https://hy.tencent.com/polices/hy-crawlers) 【官方】 — HySpider 的 UA、公开 IP 列表与 robots 控制方式；官方说明其抓取内容可能用于训练混元基础模型。
- [Kimi Crawlers](https://www.kimi.com/policies/kimi-crawlers) 【官方】 — KimiBot（训练）、Kimi-SearchBot（搜索索引）、Kimi-User（用户触发）三个爬虫的用途、UA 与 IP 列表。
- [360 搜索：Robots 协议支持](https://www.so.com/help/help_3_2.html) 【官方】 — 360Spider 的 robots 支持说明；蜘蛛 IP 见同站 [360 蜘蛛 IP](https://www.so.com/help/spider_ip.html)。
- [搜狗站长指南（含 sogou spider FAQ）](https://www.sogou.com/docs/help/webmasters.htm) 【官方】 — 搜狗 spider 的抓取频率、robots 支持与收录偏好说明。
- [神马搜索：移动网站优化指南](https://zhanzhang.sm.cn/open/optimizaGuide) 【官方】 — 写明神马搜索的爬虫 UA 为 yisouspider（2014 年文档）。
- [PetalBot（华为花瓣搜索）](https://webmaster.petalsearch.com/site/petalbot) 【官方】 — PetalBot 的 UA 与 DNS 核验方法，官方说明其索引也服务华为智能助手与 AI 搜索。
- [ai.robots.txt](https://github.com/ai-robots-txt/ai.robots.txt) 【工具】 — 社区维护的 AI 爬虫 UA 名录，可生成 robots.txt 与 nginx/Apache 配置（英文为主）。
- [AI 爬虫收录表](https://opengeo.page/tools/crawlers/) 【工具】 — 30 个国内外 AI 爬虫的 UA、用途、官方依据与 robots 写法，每条标注官方 / 实测 / 推断（维护者项目）。
- [伪装 AI 爬虫识别](https://opengeo.page/tools/crawlers/fake/) 【文章】 — 用服务器日志核验自称 AI 爬虫的请求，记录冒充案例与识别方法（维护者项目）。

## 站长平台与收录工具

- [百度搜索资源平台](https://ziyuan.baidu.com/) 【官方】 — 百度站长平台：站点验证、sitemap、普通收录与抓取诊断。
- [头条搜索站长平台](https://zhanzhang.toutiao.com/) 【官方】 — 字节跳动头条搜索的站点验证、sitemap 提交与抓取频次设置。
- [360 站长平台](https://zhanzhang.so.com/) 【官方】 — 360 搜索的站点管理与收录工具。
- [搜狗资源平台](https://zhanzhang.sogou.com/) 【官方】 — 搜狗搜索的站点提交与管理。
- [神马站长平台](https://zhanzhang.sm.cn/) 【官方】 — 神马搜索（阿里 UC 旗下移动搜索）的站长工具。
- [Bing Webmaster Tools](https://www.bing.com/webmasters/) 【官方】 — 必应站长平台，含 sitemap、URL 提交与 AI 引用报告。

## 技术标准与官方指南

- [RFC 9309: Robots Exclusion Protocol](https://www.rfc-editor.org/rfc/rfc9309) 【标准】 — robots.txt 的 IETF 正式标准。
- [IETF AI Preferences (aipref) 工作组](https://datatracker.ietf.org/wg/aipref/about/) 【标准】 — 正在制定「内容能否用于 AI 训练 / 使用」的偏好表达标准。
- [llms.txt](https://llmstxt.org/) 【标准】 — 面向大模型的站点说明文件提案；它是社区提案，不是搜索引擎承诺支持的标准。
- [schema.org](https://schema.org/) 【标准】 — 结构化数据词汇表（JSON-LD / Microdata）。
- [IndexNow 协议文档](https://www.indexnow.org/documentation) 【标准】 — IndexNow 的 key 文件、单条与批量提交格式。

## 国内法规

- [生成式人工智能服务管理暂行办法](https://www.cac.gov.cn/2023-07/13/c_1690898327029107.htm) 【法规】 — 国家网信办等七部门 2023 年发布，规范国内生成式 AI 服务。
- [人工智能生成合成内容标识办法](https://www.cac.gov.cn/2025-03/14/c_1743654684782215.htm) 【法规】 — 2025 年发布，规定 AI 生成合成内容的显式与隐式标识义务，与用 AI 批量生产 GEO 内容直接相关。

## 中文 GEO 文章与教程

- [GEO 优化怎么做：万字深度拆解生成式引擎优化](https://zhuanlan.zhihu.com/p/2032797353510482664) 【文章】 — 从 RAG 检索、重排、生成三个环节拆解 GEO，作者为前赶集 / 美团 / 知乎 SEO 负责人；文末附作者顾问服务信息。
- [品牌是怎么进入 AI 答案的：GEO 的采信机制与工程实践](https://developer.aliyun.com/article/1773314) 【文章】 — 按召回、重排、生成、引用链路讲「可召回、可对齐、可核验」三个条件和采样归因方法。
- [GEO 评测怎么做？用 A/B 实验验证 AI 引用提升是否真实有效](https://cloud.tencent.com/developer/article/2731309) 【文章】 — 讲为什么单次截图不能证明 GEO 有效，以及重复采样与对照实验的设计。
- [GEO 白皮书（Cyber Atlas）](https://joeeeeey.github.io/geo-whitepaper/) 【文章】 — 84 章的开源中文 GEO 知识图谱，含原论文解读与合规章节。

## 观测与测量工具

- [Bing AI Performance](https://www.bing.com/webmasters/help/ai-performance-9f8e7d6c) 【官方】 — 必应站长平台的 AI 引用报告：页面在 Copilot 与必应 AI 摘要中被引用的次数与对应查询；目前少有的厂商一手引用数据。
- [GEOInflow](https://github.com/yaojingang/GEOInflow) 【工具】 — 自托管的网站访客与 AI 爬虫分析，统计 AI 爬虫抓取、AI 搜索引荐流量与转化（MIT）。
- [GEORank](https://github.com/yaojingang/GEORank) 【工具】 — 开源 GEO 诊断工作台：站点检查、问答、拓词与 JSON-LD / llms.txt 生成器，中英文文档（Apache-2.0）。
- [Chinese-Geo](https://github.com/qingqingpi/Chinese-Geo) 【工具】 — 面向国内 AI 引擎的命令行体检工具，检查国内爬虫准入与百度系结构化数据，零依赖可进 CI（MIT）。
- [AI 引用来源计数器](https://opengeo.page/tools/source-counter/) 【工具】 — 粘贴 AI 回答的引用列表，按网站统计来源分布（维护者项目）。

## 社区与相关列表

- [awesome-geo-cn](https://github.com/LLM-X-Factorer/awesome-geo-cn) 【列表】 — 另一份中文 GEO 资源列表，偏工具与课程。
- [GEO Wiki 项目库](https://geo.wiki/zh/projects) 【列表】 — 中英双语的 GEO 开源项目库，按用途、许可与活跃度标注。
- [awesome-generative-engine-optimization](https://github.com/amplifying-ai/awesome-generative-engine-optimization) 【列表】 — 英文 GEO 资源指南。

## 贡献

欢迎提交 PR 补充条目或修正失效链接。收录标准、格式和禁止事项见 [CONTRIBUTING.md](CONTRIBUTING.md)。简单说：要能打开、有实质内容、一行中立描述、标好标签，不收广告和代运营软文。

## 许可

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

在法律允许的范围内，维护者已放弃本作品的全部版权及相关权利，详见 [LICENSE](LICENSE)（CC0-1.0）。
