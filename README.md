# Hyperspace 节点
## ➡️ 方法 1. 浏览器节点
* 如果你有空闲的电脑或在使用电脑工作时可以使用浏览器运行
* 你可以获得在线时间来获取倍数奖励，我是24/7全天候运行
* 你可以在 Windows 服务器上运行（如果你有安装了 Windows 的 VPS 用于其他扩展节点）

### 1. 访问: https://node.hyper.space/

### 2. 将红色按钮切换为绿色

![image](https://github.com/user-attachments/assets/727b0c1e-031b-4f5c-9bb6-60a4becaf19b)

### 3. 查看你的积分

![Screenshot_516](https://github.com/user-attachments/assets/3697612a-9ee6-4d7e-837c-f74d5cbacf8d)
![Screenshot_517](https://github.com/user-attachments/assets/6682b24d-224e-4e4c-96d3-4961a024eb77)

* 你获得的积分基于节点的在线时间、活跃度倍数和系统规格等级
* 你最初获得5级，但随着节点保持在线并有良好性能，你的等级和倍数会随时间增加

### 4. 保存你的*私钥*
你可以之后导入它

![Screenshot_518](https://github.com/user-attachments/assets/3e08837d-1261-4873-b038-e7f86222d1b2)
![Screenshot_519](https://github.com/user-attachments/assets/67506c7d-9932-462c-a4d0-29f3992d7e4a)

❗️* **确保保持红色开关打开，因为有时可能会因为网络问题而断开连接。**

#

## ➡️ 方法 2. 下载应用程序（Windows、Linux、Mac）
### 1. 访问: https://hyper.space/downloads
你可以选择 GPU 或 CPU 版本

![Screenshot_520](https://github.com/user-attachments/assets/45db8805-a579-489a-ad87-14f011332c4e)

### 2.下载模型并打开红色按钮

![image](https://github.com/user-attachments/assets/e79f90f3-7c50-4a8c-a352-712844592092)

* 你可以在这个目录找到你的私钥文件 `key.pmf`：`C:\Users\XXX\AppData\Roaming\hyperspace`

#

## ➡️ 方法 3. Linux CLI 节点（VPS）
* 我通过以下指南在我的 VPS 上获取积分，如果需要改进，我会更新仓库
* 你也可以查看[官方仓库](https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file)获取更多命令和信息

### 安装
```
curl https://download.hyper.space/api/install | bash

source /root/.bashrc
```

### 启动你的节点
```console
# 创建一个 screen 在后台运行
screen -S hyperspace

# 运行节点
aios-cli start
```
* 要继续，使用 `CTRL+A+D` 最小化你的 screen 或打开第二个终端
* 返回 screen：`screen -r hyperspace`

### 配置节点
```console
# 下载所需模型
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
# 导入你的私钥 - 使用 nano .pem 创建一个 my.pem 文件并输入私钥（你可以从浏览器版本获取私钥）
aios-cli hive import-keys ./my.pem
# 将这些密钥设置为此会话的首选密钥
aios-cli hive login
# 确保模型已注册
aios-cli hive connect
aios-cli hive select-tier 5
```
你可以升级到3级来获得2倍积分
```
aios-cli hive select-tier 3
```

### 查看积分
```
# 查看你当前的倍数和积分
aios-cli hive points
```

![Screenshot_514](https://github.com/user-attachments/assets/b840775e-6c58-4fe4-bd95-a5b876ba7de5)


# 实用命令
```console
# 如果你停止了节点，这是启动、登录和连接到 Hive 命令的快捷方式
aios-cli start --connect
# 更新节点
aios-cli version
# 停止节点
aios-cli kill
```
