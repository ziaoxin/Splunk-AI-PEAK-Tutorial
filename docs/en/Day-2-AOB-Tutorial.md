
---

# Day 2: The Game-Changing Tool Arrives — Mastering Splunk Add-on Builder (AOB)

**Today’s Goal**: Install Splunk Add-on Builder, gain a deep understanding of the configuration priority logic underlying Splunk applications, and complete the physical directory initialization of the `PEAK-llm-analyzer` add-on.

---

### Step 1: Download and Install Add-on Builder (AOB)

Splunk Add-on Builder (AOB) is an official graphical IDE specifically designed to automatically generate Python script frameworks, REST API interfaces, and configuration files.

**1.1 Download AOB from Splunkbase**
1. In your Windows browser, visit Splunk’s official add-on marketplace: [Splunkbase](https://splunkbase.splunk.com/).
2. Search for `Splunk Add-on Builder`.
3. Log in with the developer account you registered on Day 1, click **Download**, and save the `.tgz` or `.spl` installation package to your local Windows machine.

**1.2 Install AOB in Splunk**
1. Log in to the local Splunk Web interface you set up yesterday (`http://localhost:8000`).
2. Click the gear icon ⚙️ next to **Apps** in the top-left corner (Manage Apps).
3. Click **Install app from file** in the top-right corner.
4. Click **Choose File** and select the AOB installation package you just downloaded.
5. Click **Upload**.
6. After installation, if the system prompts for a restart, click to restart Splunk. Once restarted, you’ll see the green **Splunk Add-on Builder** icon in the app list on the left sidebar.

---

### Step 2: Core Knowledge — Understanding `default` vs `local`

Before actually starting to build the add-on, you must first master the "iron rule" of Splunk development.
In the future, AOB will generate a working folder for your add-on in the background. Inside this folder, there will always be two core subdirectories:

* 📁 **`default` (Default Configuration)**:
  * This is the territory of the "developer (you)".
  * All out-of-the-box configurations, default UI dashboards, and basic Python scripts are stored here.
  * **Upgrade Behavior**: When users upgrade this add-on in the future, the `default` directory will be **completely overwritten/erased**.

* 📁 **`local` (Local Configuration)**:
  * This is the territory of the "end user".
  * API Keys filled in by users, custom task intervals, fine-tuned dashboard views — all will be saved here.
  * **Priority**: The priority of `local` is **always higher** than `default`. If the same configuration file (e.g., `app.conf`) exists in both directories, Splunk will prioritize the one in `local`.
  * **Packaging Iron Rule**: As a qualified developer, **never, ever, ever package the `local` directory and distribute it to others before releasing the add-on!** (Otherwise, your API Key and local test data will be leaked to the entire world.)

---

### Step 3: Create Your First Add-on Project (PEAK-llm-analyzer)

Now, let’s use AOB to generate the underlying architecture of the project.

1. On the Splunk homepage, click to enter the **Splunk Add-on Builder** app.
2. On AOB’s main dashboard, click the prominent **Create an add-on** button.
3. Fill in the basic information strictly following the specifications below:
   * **Add-on Name**: `PEAK-llm-analyzer` *(Highlighting the identity of the PEAK Threat Hunting Framework)*
   * **Add-on Author**: Enter your name or team name (e.g., `SecOps Team`)
   * **Add-on Version**: `1.0.0`
   * **Visible**: Check `Yes` *(We need a UI entry for the independent threat report dashboards we’ll build in this add-on later)*
   * **Theme Color**: Choose a color that matches the AI geek aesthetic (e.g., dark purple or neon green).
   * **Add-on icon**: (Optional) You can upload a `50x50` PNG image as the avatar for your AI agent.

4. After confirming all information is correct, click **Create**.

*At this moment, AOB is furiously generating dozens of basic XML, `.conf`, and Python directory files in the background for you.*

---

### Step 4: Result Verification and Underlying Skeleton Inspection (Key Pitfalls to Avoid)

Don’t just settle for UI-level success — verify the setup in the Linux directory like an underlying hacker.

**4.1 Frontend UI Verification**
After creation, click `Splunk>enterprise` in the top-left corner to return to the Splunk homepage. In the App navigation bar on the left, you should clearly see the **PEAK-llm-analyzer** app with your custom icon and theme color.

**4.2 Underlying Physical Directory Verification (AOB’s Mandatory Naming Rule)**
⚠️ **Note**: AOB has a mandatory underlying rule — it automatically identifies the created app as a Technology Add-on and **forcibly prepends the `TA-` prefix to the name of the underlying physical folder**.

Open your Ubuntu WSL terminal, navigate to Splunk’s app directory, and verify the actual folder path:

```bash
# 1. Navigate to the Splunk apps directory
cd /opt/splunk/etc/apps/

# 2. Check if the add-on was generated successfully (note the TA- prefix auto-added by AOB!)
ls -ld TA-PEAK-llm-analyzer

# 3. Inspect the skeleton directory structure in detail
ls -l TA-PEAK-llm-analyzer/
```

**Expected Output**:
You’ll see a perfect directory structure similar to the following, indicating the skeleton was generated successfully:

```text
drwx------ 2 xxx xxx 4096  bin        # Where core Python scripts will be placed in the future
drwx------ 4 xxx xxx 4096  default    # Basic configurations auto-generated by AOB (out-of-the-box settings)
drwx------ 3 xxx xxx 4096  local      # Local cache auto-generated by AOB (must exclude when packaging)
drwx------ 4 xxx xxx 4096  metadata   # Permission control files
drwx------ 3 xxx xxx 4096  static     # Stores the icon you uploaded and other static resources
```

---

### 📝 Today’s Summary

**🎉 Congratulations! You’ve successfully completed the project skeleton setup for Day 2!**

Today, you not only learned to use Splunk’s premier development tool — AOB — but also mastered the `default / local` override mechanism that all advanced Splunk developers must understand. You also uncovered AOB’s underlying rule of automatically prepending the `TA-` prefix to physical folder names.

The empty `bin` directory you saw in the terminal is where we’ll inject the "AI soul" in the future. Tomorrow (Day 3), we’ll step outside Splunk’s framework and first use pure Python to unblock the "critical channels" of large model APIs, laying solid technical groundwork for implanting the AI brain! Get ready to kick off Day 3!

