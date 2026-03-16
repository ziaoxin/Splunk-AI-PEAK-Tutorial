
---
# Course Overview: 21 Days in Action - Splunk AI Threat Hunting Plugin Development

**Course Objective**: Guide zero-foundation or basic-Python security operations personnel across the barriers of Splunk's underlying architecture, developing an enterprise-grade AI security application. This app will feature multi-round autonomous reasoning based on PEAK threat hunting principles, API cost tracking, and a minimalist executive dashboard, ultimately open-sourcing it to GitHub and submitting it to the official Splunkbase plugin store.

---

## Phase 1: Environment Initialization and LLM Integration (Days 1-5)

*Phase Objective: Set up the development environment, bridge the core pathways between Splunk and the LLM, and build the plugin's skeleton.*

* **Day 1: Preparation is Key - Building the Geek Development Environment**
  * Install WSL (Windows Subsystem for Linux) or a Linux virtual machine.
  * Install and start the Splunk Enterprise developer environment via the command line in Linux.
  * Register a Splunk developer account and import the License.
  * *Goal Achieved: Successfully access the Splunk Web interface via a local browser.*

* **Day 2: A God-Tier Tool Arrives - Mastering Splunk Add-on Builder (AOB)**
  * Download and install AOB, and understand the Splunk plugin directory structure (default vs. local).
  * Create your first plugin project, configuring its version and basic information.
  * *Goal Achieved: Successfully generate the underlying architectural skeleton of the plugin within AOB.*

* **Day 3: Connecting the AI Pathways - LLM API Basics and Testing**
  * Obtain an LLM API Key (OpenAI, Ollama, or a domestic model proxy).
  * Write an external Python script to test the connectivity of LLM API requests.
  * *Goal Achieved: Familiarize yourself with the LLM's input (messages) and output (JSON) structures.*

* **Day 4: Security First - Configuring Plugin Global Credentials (Setup Parameters)**
  * Navigate AOB's UI pitfalls: How to correctly switch from the Data Input interface to the Setup page.
  * Configure the base_url, model_name, and encrypted api_key input fields.
  * *Goal Achieved: Master Splunk's underlying encrypted password vault mechanism.*

* **Day 5: Task Scheduler - Establishing the Background Data Input Stream (Data Inputs)**
  * Streamline the front-end UI: Remove redundant fields and cleverly "hijack" the system's default Index as the log query source.
  * Configure core scheduling parameters such as Interval and Target Index.
  * *Goal Achieved: Deliver a clean user operation interface that aligns seamlessly with native logic.*

---

## Phase 2: Injecting the Security Soul and Multi-Round Iterative Logic (Days 6-10)

*Phase Objective: Translate security hunting methodology into executable Python code, granting the AI the ability to "think and query."*

* **Day 6: Tapping into the Data Source - Splunk SDK for Python in Action**
  * Obtain the session_key via Context.
  * Write SPL and utilize the jobs