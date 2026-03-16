
---
# 21-Day Hands-On Tutorial: Build Splunk AI Threat Hunting Plugin with PEAK Framework
To: [Chinese Version](../README.md) 

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
   Start with [Day 1 Environment Setup Tutorial](./01.Day-1-Environment-Setup.md) and follow the sequence to complete the full hands-on practice.

---

## 📂 Repository Document Navigation

> 💡 **Learning Path**: The tutorial is divided into 5 core phases. Checkboxes marked with ✅ are published and clickable.

- [x] [__Course Overview: 21 Days in Action__](./00.Course-Overview.md)
### 🟢 Phase 1: Environment Initialization & LLM Integration (Days 1-5)
- [x] [Day 1: Building the Splunk Development Environment](./01.Day-1-Environment-Setup.md)
- [x] [Day 2: Mastering Splunk Add-on Builder (AOB)](./02.Day-2-AOB-Tutorial.md)
- [ ] Day 3: Connecting the AI Pathways - LLM API Basics and Testing
- [ ] Day 4: Security First - Configuring Plugin Global Credentials
- [ ] Day 5: Task Scheduler - Establishing the Background Data Input Stream

### 🔵 Phase 2: Core Security Logic & Iterative Analysis Workflow (Days 6-10)
- [ ] Day 6: Tapping into the Data Source - Splunk SDK for Python
- [ ] Day 7: PEAK Framework and ABLE Hypothesis Prompt Engineering
- [ ] Day 8: Autonomous Hunting Loop - Execute Phase Coding
- [ ] Day 9: Landing the Results - Act Phase Final Report Generation
- [ ] Day 10: Confronting Pain Points - The JSON Truncation Issue

### 🟣 Phase 3: Enterprise-Grade Refactoring and Optimization (Days 11-15)
- [ ] Day 11: Mandatory Constraints and max_tokens Optimization
- [ ] Day 12: Reshaping the Data Model - The Flat Events Revolution
- [ ] Day 13: Cost Tracking - Extracting LLM API Token Consumption
- [ ] Day 14: Extreme Fault Tolerance and Exception Handling
- [ ] Day 15: The Grand Unification - Code Review and Data Validation

### 🟠 Phase 4: Geek Dashboard Development and Automated Operations (Days 16-18)
- [ ] Day 16: Management Perspective Dashboard Design
- [ ] Day 17: Bypassing AOB's Front-End Restrictions
- [ ] Day 18: Shell Automation Scripts

### 🔴 Phase 5: Open Source, Packaging and Official Release (Days 19-21)
- [ ] Day 19: The Security-First Pure Packaging Method
- [ ] Day 20: GitHub Repository Construction and Release
- [ ] Day 21: Splunkbase Listing and AppInspect Certification

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
