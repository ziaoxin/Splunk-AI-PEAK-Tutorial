
---
# Splunk AI-PEAK AI威胁狩猎插件开发 21天实战教程

To: [English Version](./en/README.en.md) 

---

![GitHub Stars](https://img.shields.io/github/stars/ziaoxin/Splunk-AI-PEAK-Tutorial?style=flat-square)
![GitHub Forks](https://img.shields.io/github/forks/ziaoxin/Splunk-AI-PEAK-Tutorial?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/ziaoxin/Splunk-AI-PEAK-Tutorial?style=flat-square)
![License](https://img.shields.io/github/license/ziaoxin/Splunk-AI-PEAK-Tutorial?style=flat-square)


![Splunk](https://img.shields.io/badge/Splunk-Enterprise_10.x-black?logo=splunk)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![AI](https://img.shields.io/badge/LLM-OpenAI_Compatible-green?logo=openai)
![Status](https://img.shields.io/badge/Status-Active_Development-orange)

---

## 🎯 项目简介
本项目是一套面向**安全运营人员（SOC）、安全开发工程师、Splunk 爱好者**的实战化教程。以 PEAK 威胁狩猎框架 (Prepare, Execute, Act) 为理论基石，结合大语言模型 (LLM) 与 Splunk Add-on Builder (AOB)，手把手带你从零开发一款具备 AI 自主推理能力的企业级安全应用 `PEAK-llm-analyzer`。

通过本教程，你将完成从环境搭建、核心逻辑开发、企业级优化，到最终上架 Splunkbase 的全流程实战，打造属于你的自动化「AI 虚拟安全专家」。

## ✨ 核心特性
- 🤖 **自主威胁分析**：自动读取 Splunk 日志基线，生成 ABLE 安全假设与探索性 SPL 查询
- 🔄 **智能多轮迭代**：模拟人类专家分析逻辑，基于查询结果自动修正、生成下钻 SPL
- 💰 **API 成本全追踪**：精准记录每一轮大模型调用的 Token 消耗与对应成本
- 📊 **极简高管可视化**：深色大屏直观展示风险评分、执行轨迹与落地安全建议
- 📚 **零基础友好**：从环境搭建到上架发布，全流程分步拆解，配套可直接复用的代码与配置

---

## 🚀 快速开始
### 环境要求
- 操作系统：Windows（需开启 WSL2 + Ubuntu）、原生 Linux 或 macOS
- Splunk 版本：支持 Splunk Enterprise 8.x/9.x，需提前申请开发者授权
- 开发依赖：Python 3.7+、兼容 OpenAI 格式的大模型 API Key

### 3步开启学习
1. **克隆仓库到本地**
   ```bash
   git clone https://github.com/ziaoxin/Splunk-AI-PEAK-Tutorial.git
   cd Splunk-AI-PEAK-Tutorial
   ```
2. **完成前置准备**
   参考下方「前置准备工作」，完成 Splunk 开发者账号注册、License 申请与 API Key 准备
3. **开启学习之旅**
   从 [Day 1 环境搭建教程](<./01.Day 1：兵马未动，粮草先行 —— 零基础构建极客底层环境.md>) 开始，按顺序完成全流程实战

---

## 📂 教程目录与进度 (Table of Contents)

> 💡 **学习建议**：本教程分为 5 个核心阶段，建议从阶段一依次进行。带 ✅ 的为已发布章节，点击即可阅读。
 
>💡[__教程总览：21天实战课程介绍__](<./00.教程总览：《21天实战 Splunk AI 威胁狩猎插件开发》.md>) 

>💡已经更新到第10天，后续章节将继续完善。

### 🟢 第一阶段：环境初始化与大模型接入 (第 1-5 天)
- [x] [Day 1：兵马未动，粮草先行 —— 搭建极客开发环境](<./01.Day 1：兵马未动，粮草先行 —— 零基础构建极客底层环境.md>)
- [x] [Day 2：神器降临 —— 掌握 Splunk Add-on Builder (AOB)](<./02.Day 2：神器降临 —— 掌握 Splunk Add-on Builder (AOB).md>)
- [x] [Day 3：打通 AI 经脉 —— 大模型 API 基础与测试](<./03.Day 3：打通 AI 经脉 —— 大模型 API 基础与测试.md>)
- [x] [Day 4：安全第一 —— 配置插件全局凭证 (Setup Parameters)](<./04.Day 4：安全第一 —— 配置插件全局凭证 (Setup Parameters).md>)
- [x] [Day 5：任务调度器 —— 数据输入与“心跳”机制](<./05.Day 5：任务调度器 —— 数据输入与心跳机制.md>)

### 🔵 第二阶段：注入安全灵魂与多轮迭代逻辑 (第 6-10 天)
- [x] [Day 6：连接数据之源 —— Splunk SDK for Python 实战](<./06.Day 6：连接数据之源 —— Splunk SDK for Python 实战.md>)
- [x] [Day 7：植入顶级大脑 —— PEAK 框架与 ABLE 假设提示词工程](<./07.Day 7：植入顶级大脑 —— PEAK 框架与多维 ABLE 假设工程.md>)
- [x] [Day 8：自主狩猎循环——打造大屏友好的执行引擎](<./08.Day 8：自主狩猎循环——打造大屏友好的执行引擎.md>)
- [x] [Day 9：成果落地 —— Act 阶段最终报告生成](<./09.Day 9：成果落地——Act 阶段战报生成与大屏数据落盘.md>)
- [x] [Day 10：直面深水区 —— 总结系统痛点与底层架构重塑](<./10.Day10：直面深水区——总结系统痛点与底层架构重塑.md>)

### 🟣 第三阶段：企业级重构与极致优化 (第 11-15 天)
- [x] [Day 11：灵魂注入 —— 彻底废弃 Mock，接入真实大模型 API](<./11.Day11：灵魂注入 —— 彻底废弃 Mock，接入真实大模型.md>)
- [x] [Day 12：动态上下文提纯 —— 优化 Prompt 与防护机制](<./12.Day12：动态上下文提纯——优化 Prompt 与防护机制.md>)
- [x] [Day 13：精算师本色——真实环境下的API Token成本提取](<./13.Day13：精算师本色——真实环境下的API Token成本提取.md>)
- [x] [Day 14：混沌工程与结构防御——验证系统韧性](<./14.Day14：混沌工程与结构防御——验证系统韧性.md>)
- [x] [Day 15：底层大一统 —— 代码 Review 与数据校验](<./15.Day15：底层大一统——代码 Review 与“transaction”跨阶段数据校验.md>)

### 🟠 第四阶段：极客大屏开发与自动化运维 (第 16-18 天)
- [x] [Day 16：大屏呈现——管理层视角 Dashboard 顶级设计](<./16.Day16：大屏呈现——管理层视角 Dashboard 顶级设计.md>)
- [ ] Day 17：绕过 AOB 前端霸权 —— 底层文件注入术
- [ ] Day 18：从开发者到运维人 —— Shell 自动化脚本

### 🔴 第五阶段：开源、打包与官方发布 (第 19-21 天)
- [ ] Day 19：安全第一的纯净打包法
- [ ] Day 20：拥抱开源 —— GitHub 仓库建设与发布
- [ ] Day 21：进军殿堂 —— Splunkbase 上架与 AppInspect 认证
---

## 🛠️ 前置准备工作
1. **操作系统准备**
   - Windows 用户：提前开启 WSL2 并安装 Ubuntu 20.04/22.04 发行版
   - Linux/macOS 用户：确保系统可正常安装 Splunk Enterprise

2. **Splunk 开发凭证**
   - 注册 [Splunk 开发者账号](https://dev.splunk.com/)
   - 申请免费的开发者 License（10GB/天 索引额度）
   - 提前安装 Splunk Enterprise 并完成基础初始化

3. **AI 接口准备**
   - 准备兼容 OpenAI 格式的大模型 API Key
   - 教程默认以阿里云通义千问 DashScope 为例，可无缝替换为 DeepSeek、OpenAI、Anthropic 等主流大模型服务

---

## 🤝 贡献指南
我们非常欢迎社区贡献，无论是文档纠错、内容补充、代码优化，还是新的实战案例，都可以通过以下方式参与：

### 1. 反馈问题与建议
- 如果你发现文档错误、代码 Bug，或有内容优化建议，请通过 [GitHub Issues](https://github.com/ziaoxin/Splunk-AI-PEAK-Tutorial/issues) 提交
- 提交 Issue 时，请尽量清晰描述问题场景、复现步骤，便于我们快速定位处理

### 2. 提交内容贡献
1. **Fork 本仓库** 到你的个人 GitHub 账号
2. **创建功能分支**：建议分支命名规范 `docs/xxx-优化` / `fix/xxx-修复` / `feat/xxx-新增内容`
3. **提交修改**：Commit 信息请遵循 [Conventional Commits](https://www.conventionalcommits.org/) 规范，示例：
   - `docs: 修正 Day1 中 WSL2 环境配置步骤`
   - `fix: 补充示例代码的异常处理逻辑`
4. **发起 Pull Request**：提交 PR 到本仓库的 `main` 分支，详细说明修改内容与目的
5. **代码评审**：我们会尽快完成评审，确认无误后合并到主仓库

### 3. 文档规范
- 所有 Markdown 文档请保持格式统一，标题层级清晰，代码块标注语言类型
- 中英文术语保持统一，技术术语优先使用行业通用译法（如「威胁狩猎」对应「Threat Hunting」）
- 实操步骤请保持连贯，关键操作补充截图与说明，确保零基础用户可跟随操作

---

## 📄 许可证
本项目采用 [MIT 许可证](./LICENSE) 开源，你可以自由使用、修改、分发本项目内容，商业使用请保留原作者版权声明。

---

## 💬 交流与反馈
- 仓库讨论区：[GitHub Discussions](https://github.com/ziaoxin/Splunk-AI-PEAK-Tutorial/discussions)（优先推荐，用于技术交流、学习心得分享）
- 问题反馈：[GitHub Issues](https://github.com/ziaoxin/Splunk-AI-PEAK-Tutorial/issues)
- 🌟 如果你觉得本教程对你有帮助，欢迎 Star 收藏，也欢迎分享给更多 Splunk 与安全开发爱好者
