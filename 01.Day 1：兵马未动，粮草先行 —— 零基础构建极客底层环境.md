
---

# 🚀 Day 1：兵马未动，粮草先行 —— 零基础构建Splunk开发环境

**今日目标**：在本地搭建一个纯净的、具备完整读写权限且解锁了企业级高级功能的 Linux (WSL2) Splunk 开发者实验室。

### 💡 为什么必须用 Linux / WSL2？

Splunk 的 Add-on Builder (AOB) 以及底层的文件权限机制（如 `.sh` 脚本执行、文件路径分隔符等）在 Windows 下极易出现反直觉的 Bug。使用 **WSL2 (Windows Subsystem for Linux 2)** 是目前最优雅、性能最好、且最接近生产环境的本地开发方案。

---

### 🛠️ Step 1：WSL2 与 Ubuntu LTS 深度安装与校验

为了保证未来的插件打包和 Python 环境不出诡异的 Bug，我们必须确保安装的是**最新版的 Ubuntu 长期支持版 (LTS)**，且底层架构为纯正的 WSL2。

请在 Windows 中以**管理员身份**打开 PowerShell，严格按照以下步骤执行：

#### 1.1 目前状态检测 (State Check)

在 PowerShell 中输入以下命令查看当前 WSL 的状态，摸清底牌：

```powershell
wsl -l -v

```

* **情况 A（绿灯）**：提示 `wsl is not recognized...` 或连接超时，说明你的电脑是张白纸，完美！
* **情况 B（黄灯）**：列出了其他发行版。只要不影响工作可保留；若想推倒重来，可用 `wsl --unregister <发行版名称>` 卸载。

查看微软官方应用商店目前提供的可用 Linux 列表：

```powershell
wsl --list --online

```

#### 1.2 指定安装 Ubuntu 最新长期支持版 (Install LTS)

不要使用默认的 `wsl --install`（那像开盲盒），我们要精准狙击最新的 LTS 版本（假设目前最新为 24.04）：

```powershell
wsl --install -d Ubuntu-24.04

```

**⚠️ 关键提醒**：若命令行跑到一半提示你需要**重启计算机 (Restart required)**，请务必重启。重启后 WSL 会自动弹出一个终端窗口继续安装。

安装尾声，Ubuntu 终端会要求你创建一个系统默认的 UNIX 账号：

* `Enter new UNIX username:` 输入一个简短的英文名（如 `hunter` 或 `admin`）。
* `New password:` 输入密码（**注意：Linux 终端下输入密码没有任何星号提示，请盲打完直接回车**）。

#### 1.3 安装结果深度确认 (Verification)

**第一重校验：确认 WSL 架构版本（在 Windows PowerShell 中执行）**

```powershell
wsl -l -v

```

输出结果中的 `VERSION` 这一列**必须是 2**！如果是 1，说明装成了残血版（可通过 `wsl --set-version Ubuntu-24.04 2` 强行升级）。

**第二重校验：确认 Linux 内部发行版（在刚才配置好的 Ubuntu 终端中执行）**

```bash
cat /etc/os-release

```

输出中应包含类似 `PRETTY_NAME="Ubuntu 24.04 LTS"` 的字眼。

---

### 🛠️ Step 2：注册开发者账号与获取“免死金牌”

Splunk 默认的 Free 试用版会锁定核心功能。为了完整开发 AI 插件，我们必须白嫖一张官方发给开发者的 **10GB/天、有效期半年的 Developer License**。

1. 在 Windows 浏览器中，打开 Splunk 开发者官网：[dev.splunk.com](https://dev.splunk.com/)
2. 点击右上角的 **Sign Up**，填写真实邮箱完成注册并登录。
3. 在顶部导航栏找到 **Enterprise** -> **Get a Developer License**（或在个人主页寻找 Request License）。
4. 勾选同意开发者条款，点击 **Request License**。
5. 下载生成的 `splunk.license` XML 文件。**把这个文件保存在你的 Windows 桌面或下载文件夹中备用。**

---

### 🛠️ Step 3：通过命令行精确下载 Splunk Enterprise

作为极客，我们直接在 Linux 终端里用 `wget` 高速拉取安装包。

1. 在 Windows 浏览器登录 Splunk 官网，访问 **Free Trials & Downloads** -> **Splunk Enterprise**。
2. 操作系统选择 **Linux**，格式选择 **.tgz**。
3. 点击 Download 后，**立即取消 Windows 浏览器的下载**。找到页面右侧的 **"Download via Command Line (wget)"**，复制那段黑框里的完整命令。
4. 回到你的 Ubuntu WSL 终端，更新软件源并执行下载（请将引号内的链接替换为你刚刚复制的真实链接）：

```bash
# 1. 更新软件源并确保 wget 已安装
sudo apt update && sudo apt install wget -y

# 2. 粘贴你复制的 wget 命令拉取安装包
wget -O splunk-Linux-x86_64.tgz "https://download.splunk.com/products/splunk/releases/9.x.x/linux/splunk-9.x.x-xxxxxxx-Linux-x86_64.tgz"

```

---

### 🛠️ Step 4：解压与目录权限配置 (核心避坑点！)

在 Linux 世界，第三方大型软件的标配家园是 `/opt` 目录，但它默认属于 `root`。**如果你用 root 权限运行 Splunk，后期 AOB 生成的代码你也无法修改！** 必须进行“鸠占鹊巢”：

1. **借用最高权限解压文件到 `/opt` 目录**：

```bash
sudo tar -xzvf splunk-*.tgz -C /opt

```

2. **转移目录所有权（极其重要）**：
将整个 Splunk 文件夹的所有权，移交给当前的普通 UNIX 账户（`$USER` 代表你当前的用户名）：

```bash
sudo chown -R $USER:$USER /opt/splunk

```

*执行完这条命令，你就是 `/opt/splunk` 的绝对主宰！*

---

### 🛠️ Step 5：点火启动与注入 License

万事俱备，开启引擎并解除功能封印。

#### 5.1 首次启动并初始化账号

```bash
# 1. 进入 Splunk 的可执行文件目录
cd /opt/splunk/bin

# 2. 启动引擎，并自动同意协议条款
./splunk start --accept-license

```

终端会要求你创建**最高权限的本地管理员账号**：

* 输入 username: `admin`
* 输入 password: `changeme` (盲打输入，回车确认，需输入两次)。

当终端打印出 `The Splunk web interface is at http://<计算机名或IP>:8000` 时，启动成功！

#### 5.2 登录 Web 界面与导入 License

1. 打开 Windows 浏览器，访问：`http://localhost:8000` *(若无法访问，在 Ubuntu 终端输入 `ip a` 找 eth0 的 IP，用该 IP 访问)*。
2. 使用 `admin` 和 `changeme` 登录。
3. 在 Splunk 顶部黑色的系统导航栏，点击 **Settings (设置)** -> **Licensing (许可)**。
4. 点击绿色的 **Add license** 按钮。
5. 选择 **Choose file**，从 Windows 桌面上选中 Step 2 下载的 `splunk.license` 文件，点击 **Install**。
6. 点击页面上的 **Restart Splunk** 按钮重启系统。

---

### ✅ 最终结果确认 (今日里程碑达成)

等待 Splunk 重启完毕并再次登录后：

1. 再次进入 **Settings** -> **Licensing**。
2. 在 License 组中清晰地看到 **Enterprise (Developer)** 字样。
3. 确认拥有每天 **10,240 MB (10GB)** 的可用索引额度。

**🎉 恭喜你！Day 1 的硬核基础设施搭建完美收官！**
现在你拥有了一个权限完美配置、核心功能全开、运行在原生 Linux 内核上的企业级开发平台。好好休息，明天（Day 2），我们将正式请出开发神器 Splunk Add-on Builder，拉开代码建设的帷幕！