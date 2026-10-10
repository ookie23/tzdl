# 堂主代练

> 🎮 一款轻量级的 Windows 自动化按键工具，内置鼠标漂移和自定义节奏控制

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Stable-brightgreen.svg)

---

## 📖 简介

**堂主代练** 是一款基于 Python 开发的 Windows 桌面自动化工具，主要用于需要长时间重复按键的场景。它支持键盘（空格键、F键）与鼠标左键的随机组合触发，并通过鼠标位置漂移、按键间隔随机化等机制，让自动化操作更接近真人使用习惯。

软件采用 Tkinter 图形界面，操作简单，配置持久化，适合作为日常辅助工具或自动化测试工具使用。

---

## ✨ 功能特性

### 按键组合
- 支持 **空格键 / F键 / 鼠标左键** 三种输入
- 可单独触发、两两组合或三键同时按下
- 每次随机选择，避免固定模式

### 鼠标漂移
- 启动时以当前鼠标位置为初始锚点
- 每次点击在设定范围内随机偏移（默认 3-14 像素）
- 偏移后自动更新锚点，鼠标位置持续自然漂移

### 自定义节奏
- 按键间隔 0-1 秒随机
- 运行时长可自定义（默认 30-40 秒）
- 暂停时长可自定义（默认 2-4 秒）
- 自动循环，无需手动干预

### 控制方式
- **全局键盘热键**：默认 F8，可自由更换
- **鼠标侧键**：支持罗技 G102 等带侧键的鼠标
- **界面按钮**：一键启停

### 其他特性
- 🔊 启动/停止提示音
- 💾 配置自动保存（热键、侧键绑定）
- 🪟 窗口置顶显示
- 🎨 自定义软件图标

---

## 🚀 快速开始

### 方式一：下载使用

前往 [Releases](../../releases) 页面下载 `堂主代练.exe`，右键选择 **以管理员身份运行**。

> ⚠️ 首次运行需要管理员权限，否则全局热键可能失效。

### 方式二：从源码运行

```bash
# 克隆仓库
git clone https://github.com/yourusername/tangzhu-auto.git
cd tangzhu-auto

# 安装依赖
pip install -r requirements.txt

# 运行
python main.py
```

### 方式三：自行打包

```bash
pip install pynput pyinstaller
pyinstaller --onefile --windowed --name "堂主代练" --icon=icon.ico --add-data "icon.ico;." main.py
```

---

## 🖼️ 界面说明

| 区域 | 功能 |
|------|------|
| **按键选项** | 勾选需要自动触发的按键 |
| **鼠标偏移设置** | 设置鼠标点击位置的随机偏移范围 |
| **自动暂停设置** | 自定义运行时长与暂停时长 |
| **热键设置** | 设置键盘热键（默认 F8） |
| **鼠标侧键设置** | 绑定鼠标侧键作为启停开关 |
| **启动/停止** | 手动控制运行状态 |

---

## ⚙️ 配置说明

程序会在同目录生成 `config.json` 文件，保存以下设置：

```json
{
    "hotkey": "<f8>",
    "mouse_side": "x1"
}
```

删除该文件可重置所有设置。

---

## 🎯 使用场景

- 📺 需要跳过冗长对话的剧情类游戏
- 🔄 重复性日常任务处理
- 🧪 UI 自动化测试
- 📝 批量表单填写

---

## 🛠️ 技术栈

| 技术 | 用途 |
|------|------|
| Python 3.7+ | 主要开发语言 |
| Tkinter | 图形用户界面 |
| pynput | 键鼠事件模拟 |
| winsound | 提示音播放 |
| PyInstaller | 打包为独立 exe |

---

## 📁 项目结构

```
tangzhu-auto/
├── main.py              # 主程序
├── icon.ico             # 软件图标
├── requirements.txt     # 依赖列表
├── README.md            # 项目说明
├── LICENSE              # 开源协议
├── .gitignore           # Git 忽略规则
└── screenshots/         # 界面截图（可选）
```

---

## ❓ 常见问题

**Q: 为什么需要管理员权限？**  
A: 全局热键和键鼠事件模拟需要在管理员权限下才能在某些程序中生效。

**Q: 杀毒软件报毒怎么办？**  
A: PyInstaller 打包的 exe 常被误报，这是行业常见现象。源码完全开源，可以自行审计或添加信任。

**Q: 如何更换热键？**  
A: 点击界面中的"设置"按钮，然后按下想要的热键即可。

**Q: 配置文件在哪里？**  
A: 程序同目录下的 `config.json`，删除可重置。

**Q: 支持其他操作系统吗？**  
A: 目前仅支持 Windows，因为使用了 `winsound` 和 Windows API。

---

## ⚠️ 免责声明

- 本软件**完全免费**，仅供学习交流和自动化测试使用
- 请勿将本软件用于任何商业用途或违法活动
- 使用本软件可能违反部分软件或游戏的服务条款
- 因使用本软件产生的一切后果由使用者自行承担

---

## 📄 开源协议

本项目基于 [MIT License](LICENSE) 开源发布。

---

## 🤝 贡献

欢迎通过以下方式参与：

- 提交 [Issue](../../issues) 反馈问题或建议
- 提交 [Pull Request](../../pulls) 改进代码
- 给项目点个 ⭐ Star 支持

---

## 📬 联系方式

- GitHub: [@yourusername](https://github.com/yourusername)
- Email: your@email.com

---

<div align="center">

**如果这个项目对你有帮助，欢迎点个 ⭐ Star！**

</div>
