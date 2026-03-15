---
# 21-Day Hands-On Tutorial: Build Splunk AI Threat Hunting Plugin with PEAK Framework
[中文版本 (Chinese Version)](./README.md) | [Full Tutorial Overview (Chinese)](./🚀%20教程总览：《21天实战%20Splunk%20AI%20威胁狩猎插件开发》.md)

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

## 🎯 Project Overview
This is a hands-on tutorial designed for **Security Operations Center (SOC) analysts, security development engineers, and Splunk enthusiasts**. Based on the industry-leading PEAK Threat Hunting Framework (Prepare, Execute, Act), combined with Large Language Models (LLM) and Splunk Add-on Builder (AOB), this tutorial walks you through building an enterprise-grade security application `PEAK-llm-analyzer` with AI autonomous reasoning capabilities from scratch.

By following this tutorial, you will complete the full lifecycle of Splunk App development: from environment setup, core logic development, enterprise-grade optimization, to final publishing on Splunkbase, and build your own automated "AI Virtual Security Expert".

## ✨ Key Features
- 🤖 **Autonomous Threat Analysis**: Automatically read Splunk log baselines, generate ABLE security hypotheses and exploratory SPL queries
- 🔄 **Intelligent Iterative Analysis**: Simulate human expert reasoning, automatically refine and generate drill-down SPL based on previous query results
- 💰 **Full API Cost Tracking**: Precisely record Token consumption and corresponding costs for each LLM API call
- 📊 **Executive-Friendly Visualization**: Dark-themed dashboard to clearly display risk scores, execution trails and actionable security recommendations
- 📚 **Zero-Beginner Friendly**: Step-by-step breakdown of the full workflow, with ready-to-use code and configuration samples

---

## 📂 Repository Document Navigation
| Document Name | Core Content | Link |
|---------------|--------------|------|
| Full Tutorial Overview | Complete curriculum system, learning path and core objectives (Chinese) | [View](./🚀%20教程总览：《21天实战%20Splunk%20AI%20威胁狩猎插件开发》.md) |
| Day 1 Environment Setup | Zero-to-One Splunk development environment build (WSL2 & Splunk Deployment) (Chinese) | [View](./🚀%20Day%201：兵马未动，粮草先行%20——%20零基础构建极客底层环境.md) |
| Day 2 AOB Fundamentals | Core usage of Splunk Add-on Builder and underlying plugin directory structure (Chinese) | [View](./🚀%20Day%202：神器降临%20——%20掌握%20Splunk%20Add-on%20Builder%20(AOB).md) |

> 🔔 Upcoming tutorials (Day3-Day21) will be updated continuously. Please Star the repository to stay tuned.

---

## 🚀 Quick Start
### Prerequisites
- Operating System: Windows (with WSL2 + Ubuntu enabled), native Linux or macOS
- Splunk Version: Splunk Enterprise 8.x/9.x, with valid developer license
- Development Dependencies: Python 3.7+, LLM API Key compatible with OpenAI format

### 3 Steps to Get Started
1. **Clone the repository to your local machine**
   ```bash
   git clone https://github.com/ziaoxin/Splunk-AI-PEAK-Tutorial.git
   cd Splunk-AI-PEAK-Tutorial
   ```
2. **Complete Preparations**
   Refer to the "Prerequisites & Preparation" section below to register a Splunk developer account, apply for a license, and prepare your LLM API Key.
3. **Start Your Learning Journey**
   Start with [Day 1 Environment Setup Tutorial](./🚀%20Day%201：兵马未动，粮草先行%20——%20零基础构建极客底层环境.md) and follow the sequence to complete the full hands-on practice.

---

## 📚 Full Tutorial Syllabus
This tutorial is divided into 5 core phases, with a total of 21 days of hands-on content. It is strongly recommended to learn in order:

### 🟢 Phase 1: Environment Initialization & LLM Integration
- Day 1: Zero-to-One Splunk Development Environment Setup (WSL2 & Splunk)
- Day 2: Master Splunk Add-on Builder (AOB) and Underlying Plugin Directory Logic
- Day 3: LLM API Fundamentals and Python Call Testing
- Day 4: Plugin Global Credentials and Security Configuration (Setup Parameters)
- Day 5: Background Data Input Stream and Task Scheduler Setup (Data Inputs)

### 🔵 Phase 2: Core Security Logic & Iterative Analysis Workflow
- Day 6: Full Hands-On Guide to Splunk SDK for Python
- Day 7: PEAK Threat Hunting Framework Core Logic and Prompt Engineering
- Day 8: Autonomous Hunting Loop - Core Code Development for Execute Phase
- Day 9: Results Delivery - Final Security Report Generation for Act Phase
- Day 10: Data Persistence and Key Pain Point Resolution - JSON Truncation Fix

### 🟣 Phase 3: Enterprise-Grade Refactoring and Optimization
- Day 11: LLM Output Constraints and max_tokens Optimization
- Day 12: Flat Events Data Model Refactoring
- Day 13: LLM API Token Consumption Extraction and Cost Tracking System Build
- Day 14: Full-Link Fault Tolerance and Exception Handling Mechanism Development
- Day 15: Full Code Review and Data Validation Logic Closure

### 🟠 Phase 4: Visual Dashboard Development and Automated Operations
- Day 16: Executive-Focused Dashboard and Dark Theme Screen Design
- Day 17: Underlying File Injection to Bypass AOB Frontend Restrictions
- Day 18: Shell Automation Script Development for Plugin Deployment and Operations

### 🔴 Phase 5: Open Source, Packaging and Official Release
- Day 19: Security-Compliant Clean Plugin Packaging Method
- Day 20: GitHub Open Source Repository Setup and Version Release
- Day 21: Splunkbase Publishing Process and AppInspect Certification Walkthrough

---

## 🛠️ Prerequisites & Preparation
1. **Operating System Preparation**
   - For Windows users: Enable WSL2 in advance and install Ubuntu 20.04/22.04 LTS
   - For Linux/macOS users: Ensure your system supports Splunk Enterprise installation

2. **Splunk Development Credentials**
   - Register a [Splunk Developer Account](https://dev.splunk.com/)
   - Apply for a free Developer License (10GB/day indexing quota)
   - Install Splunk Enterprise in advance and complete basic initialization

3. **AI Interface Preparation**
   - Prepare an LLM API Key compatible with the OpenAI format
   - The tutorial uses Alibaba Cloud Tongyi Qianwen DashScope as the default example, which can be seamlessly replaced with mainstream LLM services such as DeepSeek, OpenAI, Anthropic, etc.

---

## 🤝 Contributing Guide
We warmly welcome community contributions, whether it's document correction, content supplement, code optimization, or new practical cases. You can participate in the following ways:

### 1. Feedback Issues and Suggestions
- If you find document errors, code bugs, or have content optimization suggestions, please submit them via [GitHub Issues](https://github.com/ziaoxin/Splunk-AI-PEAK-Tutorial/issues)
- When submitting an issue, please clearly describe the problem scenario and reproduction steps to help us quickly locate and handle it.

### 2. Submit Content Contributions
1. **Fork this repository** to your personal GitHub account
2. **Create a feature branch**: Recommended branch naming convention `docs/xxx-optimization` / `fix/xxx-bugfix` / `feat/xxx-new-content`
3. **Commit your changes**: Commit messages should follow the [Conventional Commits](https://www.conventionalcommits.org/) specification, examples:
   - `docs: fix WSL2 environment configuration steps in Day1`
   - `fix: add exception handling logic to sample code`
4. **Initiate a Pull Request**: Submit a PR to the `main` branch of this repository, detailing the modified content and purpose.
5. **Code Review**: We will complete the review as soon as possible and merge it into the main repository after confirmation.

### 3. Document Specification
- All Markdown documents should maintain a unified format, clear title hierarchy, and language type marked for code blocks.
- Keep the Chinese and English terminology unified, and give priority to industry-standard translations for technical terms.
- The operation steps should be coherent, with screenshots and explanations for key operations, to ensure that zero-beginner users can follow the operations.

---

## 📄 License
This project is open source under the [MIT License](./LICENSE). You are free to use, modify, and distribute the content of this project. Please retain the original author's copyright notice for commercial use.

---

## 💬 Discussion & Feedback
- Repository Discussions: [GitHub Discussions](https://github.com/ziaoxin/Splunk-AI-PEAK-Tutorial/discussions) (Recommended for technical exchanges and learning experience sharing)
- Issue Feedback: [GitHub Issues](https://github.com/ziaoxin/Splunk-AI-PEAK-Tutorial/issues)
- 🌟 If you find this tutorial helpful, please give us a Star to support our work, and feel free to share it with other Splunk and security development enthusiasts.
