# 🚀 21天实战：基于 PEAK 框架的 Splunk AI 威胁狩猎插件开发指南

![Splunk](https://img.shields.io/badge/Splunk-Enterprise_10.x-black?logo=splunk)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![AI](https://img.shields.io/badge/LLM-OpenAI_Compatible-green?logo=openai)
![Status](https://img.shields.io/badge/Status-Active_Development-orange)

欢迎来到 **Splunk-PEAK-Threat-Hunting-Tutorial**！本仓库记录了一场硬核的安全开发之旅。在这里，我们将跨越 Splunk 底层架构的壁垒，从零开始，手把手带你开发出一款具备 **AI 自主推理、API 成本追踪、极简高管大屏** 的企业级安全应用：`PEAK-llm-analyzer`。

## 🎯 项目简介

本项目是一套面向安全运营人员（SOC）、安全开发工程师及 Splunk 爱好者的实战化教程。

我们将以当今最前沿的 **PEAK 威胁狩猎框架 (Prepare, Execute, Act)** 为理论基石，结合强大的 **大语言模型 (LLM)** 和 **Splunk Add-on Builder (AOB)**，打造一个自动化的“AI 虚拟安全专家”。它能够：
- 🤖 **自主分析**：读取 Splunk 日志基线，自动生成 ABLE 假设和探索性 SPL 查询。
- 🔄 **多轮迭代**：像人类专家一样，根据上一次的查询结果，自动修正并生成下一轮下钻 SPL。
- 💰 **成本追踪**：精确记录每一轮 API 调用的 Token 消耗与成本。
- 📊 **战报输出**：在极简的深色大屏上，直观展示最终风险评分、执行轨迹与安全建议。

## 📚 教程大纲 (Syllabus)

本教程共分为 21 天（5 个核心阶段），强烈建议按照顺序进行阅读和实战：

### 🟢 阶段一：环境初始化与大模型接入
- Day 1：兵马未动，粮草先行 —— 搭建极客开发环境 (WSL2 & Splunk)
- Day 2：神器降临 —— 掌握 Splunk Add-on Builder (AOB) 与底层目录逻辑
- Day 3：打通 AI 经脉 —— 大模型 API 基础与 Python 测试
- Day 4：安全第一 —— 配置插件全局凭证 (Setup Parameters)
- Day 5：任务调度器 —— 建立后台数据输入流 (Data Inputs)

### 🔵 阶段二：注入安全灵魂与多轮迭代逻辑
- Day 6：连接数据之源 —— Splunk SDK for Python 实战
- Day 7：植入顶级大脑 —— PEAK 框架与提示词工程
- Day 8：自主狩猎循环 —— Execute 阶段代码编写
- Day 9：成果落地 —— Act 阶段最终报告生成
- Day 10：初次落盘与痛点遭遇 —— 直面 JSON 截断问题

### 🟣 阶段三：企业级重构与极致优化
- Day 11：对症下药 —— 强制约束与 `max_tokens` 优化
- Day 12：重塑数据模型 —— 扁平化日志 (Flat Events) 革命
- Day 13：成本追踪 —— 提取大模型 API Token 消耗
- Day 14：打造“防弹衣” —— 极限容错与异常处理
- Day 15：底层大一统 —— 代码 Review 与数据校验

### 🟠 阶段四：极客大屏开发与自动化运维
- Day 16：降维打击 —— 管理层视角 Dashboard 设计
- Day 17：绕过 AOB 前端霸权 —— 底层文件注入术
- Day 18：从开发者到运维人 —— Shell 自动化脚本

### 🔴 阶段五：开源、打包与官方发布
- Day 19：安全第一的纯净打包法
- Day 20：拥抱开源 —— GitHub 仓库建设与发布 (本特别篇)
- Day 21：进军殿堂 —— Splunkbase 上架与 AppInspect 认证

*(注：链接将随着文档的更新逐步点亮 💡)*

## 🛠️ 前置技术栈与准备工作

要无缝跟随本教程，你需要准备：
1. **操作系统**：Windows (需开启 WSL2/Ubuntu) 或 原生 Linux/Mac 环境。
2. **开发凭证**：注册 Splunk 开发者账号，并获取免费的 10GB/天 Developer License。
3. **AI 秘钥**：一个兼容 OpenAI 格式的大模型 API Key（教程中以阿里云通义千问 DashScope 为例，也可无缝替换为 DeepSeek、OpenAI 等）。

## 🤝 参与贡献

如果你在实战过程中发现了文档的纰漏、代码的 Bug，或者有更优雅的实现方案，欢迎随时提交 **Issue** 或 **Pull Request**！
让我们一起完善这份指南，帮助更多的安全从业者拥抱 AI 时代。

---
*Disclaimer: 本教程仅供技术研究与学习交流使用。在生产环境部署任何自动化脚本前，请务必进行充分的隔离测试。*
