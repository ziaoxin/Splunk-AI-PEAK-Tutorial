
---

# 🚀 Day 2：神器降临 —— 掌握 Splunk Add-on Builder (AOB)

**今日目标**：在 Splunk 中安装 Add-on Builder，深刻理解 Splunk 应用底层的配置优先级逻辑，并完成 `PEAK-llm-analyzer` 插件的物理目录初始化。

### 🛠️ Step 1：下载并安装 Add-on Builder (AOB)

Splunk Add-on Builder 是官方提供的一款图形化 IDE，专门用来自动生成 Python 脚本框架、REST API 接口和配置文件。

**1.1 从 Splunkbase 下载 AOB**

1. 在你的 Windows 浏览器中，访问 Splunk 的官方插件商店：[Splunkbase](https://splunkbase.splunk.com/)。
2. 搜索 `Splunk Add-on Builder`。
3. 使用你 Day 1 注册的开发者账号登录，点击 **Download**，下载 `.tgz` 或 `.spl` 安装包到你的 Windows 本地。

**1.2 在 Splunk 中安装 AOB**

1. 登录你昨天搭建好的本地 Splunk Web 界面 (`http://localhost:8000`)。
2. 点击左上角的 **Apps (应用)** 齿轮图标 ⚙️（Manage Apps / 管理应用）。
3. 点击右上角的 **Install app from file (从文件安装应用)**。
4. 点击 **Choose File**，选中你刚才下载的 AOB 安装包。
5. 点击 **Upload (上传)**。
6. 安装完成后，如果系统提示需要重启，请点击重启。重启后，你在左侧应用列表中就能看到绿色的 **Splunk Add-on Builder** 图标了。

---

### 🧠 Step 2：硬核知识 —— 理解 `default` vs `local`

在真正动手创建插件前，必须先掌握 Splunk 开发的“铁律”。
未来 AOB 会在底层为你的插件生成一个工作文件夹。在这个文件夹里，永远会有两个核心子目录：

* 📁 **`default` (默认配置)**：
* **这是属于“开发者（你）”的领地。**
* 所有出厂自带的配置、默认的 UI 大屏、基础的 Python 脚本都放在这里。
* **升级行为**：当用户未来升级这个插件时，`default` 目录会被**完全覆盖/抹除**。


* 📁 **`local` (本地配置)**：
* **这是属于“最终用户”的领地。**
* 用户填写的 API Key、自定义的任务间隔、微调的大屏视图，都会保存在这里。
* **优先级**：`local` 的优先级**永远高于** `default`。如果两边都有相同的配置文件（如 `app.conf`），Splunk 会以 `local` 里的为准。
* **打包铁律**：作为一个合格的开发者，**在发布插件前，绝对、绝对、绝对不能把 `local` 目录打包发给别人！**（否则你的 API Key 和本地测试数据就会泄露给全世界）。



---

### 🛠️ Step 3：创建你的第一个插件项目 (PEAK-llm-analyzer)

现在，让我们用 AOB 生成项目的底层架构。

1. 在 Splunk 首页，点击进入 **Splunk Add-on Builder** 应用。
2. 在 AOB 的大屏首页，点击醒目的 **Create an add-on (创建附加组件)** 按钮。
3. 严格按照以下规范填写基本信息：
* **Add-on Name**: `PEAK-llm-analyzer` *(彰显 PEAK 威胁狩猎框架身份)*
* **Add-on Author**: 填入你的名字或团队名（如 `SecOps Team`）
* **Add-on Version**: `1.0.0`
* **Visible**: 勾选 `Yes` *(因为我们后期要在这个插件里展示独立的战报大屏，需要 UI 入口)*
* **Theme Color**: 选一个符合 AI 极客气质的颜色（比如深紫色或荧光绿）。
* **Add-on icon**: （可选）你可以上传一张 `50x50` 的 PNG 图片作为 AI 智能体的头像。


4. 确认无误后，点击 **Create**。

*此时，AOB 正在后台疯狂为你编写几十个基础的 XML、`.conf` 和 Python 目录文件。*

---

### ✅ Step 4：结果验证与底层骨架巡检 (核心避坑点)

不要仅仅满足于 UI 上的成功，我们要像底层黑客一样去 Linux 目录里验证它。

**4.1 前端 UI 验证**
创建完成后，点击左上角的 `Splunk>enterprise` 回到 Splunk 首页。在左侧的 App 导航栏中，你应该能清晰地看到带有你专属 Icon 和颜色的 **PEAK-llm-analyzer** 应用。

**4.2 底层物理目录验证 (AOB 命名强规则)**
⚠️ **注意**：AOB 有一个底层强制规则，它会自动将创建的应用识别为技术附加组件（Technology Add-on），并**强制在底层物理文件夹名称前加上 `TA-` 前缀**。

打开你的 Ubuntu WSL 终端，进入 Splunk 的应用目录，验证真实的文件夹路径：

```bash
# 1. 进入 Splunk apps 目录
cd /opt/splunk/etc/apps/

# 2. 查看插件是否成功生成 (注意 AOB 自动加上的 TA- 前缀！)
ls -ld TA-PEAK-llm-analyzer

# 3. 深入查看骨架目录结构
ls -l TA-PEAK-llm-analyzer/

```

**预期输出：**
你会看到类似如下的完美目录结构，这意味着骨架生成极其成功：

```text
drwx------ 2 xxx xxx 4096  bin        # 未来放核心 Python 脚本的地方
drwx------ 4 xxx xxx 4096  default    # AOB 自动生成的基础配置 (出厂设置)
drwx------ 3 xxx xxx 4096  local      # AOB 目前自动生成的一些本地缓存 (打包时需排除)
drwx------ 4 xxx xxx 4096  metadata   # 权限控制文件
drwx------ 3 xxx xxx 4096  static     # 存放你刚才上传的 Icon 和静态资源

```

---

### 📝 今日总结

**🎉 恭喜你！Day 2 的工程骨架搭建顺利完成！**

今天你不仅学会了如何使用 Splunk 的第一开发利器 AOB，还掌握了高阶开发者必须深刻理解的 `default / local` 覆盖机制，并且摸清了 AOB 底层自动补充 `TA-` 前缀的物理路径规则。

你刚才在终端里看到的那个空荡荡的 `bin` 目录，就是我们未来注入 AI 灵魂的地方。明天（Day 3），我们将跳出 Splunk 的框架，先用纯 Python 打通大模型 API 的“任督二脉”，为植入 AI 大脑做好充足的技术储备！随时准备开启 Day 3！