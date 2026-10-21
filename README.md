<div align="center">

# 🌿 华农 OJ 美化 · SCAU OJ Refined

**给华南农业大学在线评测系统（OJ）换一套现代皮肤，并顺手修掉几个原生 Bug**

![version](https://img.shields.io/badge/version-2.35.0-15803d)
![platform](https://img.shields.io/badge/platform-Tampermonkey-22c55e)
![browser](https://img.shields.io/badge/browser-Chrome%20%2F%20Edge%20%2F%20Firefox-43a047)
![license](https://img.shields.io/badge/license-MIT-86c36b)

一键把"十年前风格"的教学 OJ，变成清爽的浅绿现代界面。

</div>

---

## 📸 效果预览


| 首页仪表盘（提交活跃度热力图） | 登录页 |
| :---: | :---: |
| ![dashboard](images/dashboard.png) | ![login](images/login.png) |

| 题库 / 题目列表 | 题面排版 |
| :---: | :---: |
| ![problems](images/problems.png) | ![problem](images/problem.png) |

| 提交列表 | 代码编辑器 |
| :---: | :---: |
| ![list](images/list.png) | ![submit](images/submit.png) |

---

## ✨ 功能特性

### 1. 全新视觉设计
- 🎨 全站统一为**浅绿 SaaS 风格**（华农绿主色调），卡片化内容、圆角与柔和阴影。
- 🧭 顶栏重排：用户信息整理成「头像 + 姓名 + 学号 + Grade 徽章」，图标全部换成简洁线条 SVG。
- 🪟 登录页重做：华农紫荆花背景 + 品牌区 + 毛玻璃登录卡片。

### 2. 提交活跃度热力图（核心亮点）
- 📊 首页新增 **Codeforces 风格的年度提交热力图**，颜色深浅代表当天提交量。
- 📅 支持**年份切换**、悬停查看当天提交次数。
- 🔢 自动统计：**总提交、近一年 / 近一月提交数、最长连续提交天数**等指标。
- 💾 数据按学号分桶存储、后台自动同步、**断点续传**，刷新页面不会重复抓取。

### 3. 题库与题目体验
- 📁 题目目录树美化，支持**搜索过滤**、层级引导线与折叠箭头。
- 📈 题目列表增加**通过率**统计，按比例配色。
- 📝 题面排版优化：标题分级、时限 / 内存 / 通过数整理成信息卡片。
- 💻 代码块支持**语法高亮、行号、一键复制**。

### 4. 代码编辑器增强
- ⌨️ 等宽字体、`Tab` 自动缩进、回车自动继承缩进。
- ⚡ `Ctrl / Cmd + Enter` 快速提交。
- 🔍 `Ctrl + 滚轮` 调节字号（自动记忆）。
- 🗂️ 草稿**自动保存**，误关页面可恢复。

### 5. 智能状态识别
- 🏷️ 评测结果自动渲染为彩色胶囊：**AC / WA / TLE / MLE / RE / CE / PD** 等。
- 🔘 按钮分级、考试状态着色、排行榜前三名金银铜高亮。

### 6. 顺手修复的原生 Bug
- 🐛 修复点「查看」提交列表时**等待页卡死、被带回主页**的问题，现在倒计时结束即可正常进入。
- 🐛 修复登录后 3 秒被强制跳转到个人信息页。
- 🐛 修复「粘贴」按钮失效（仅 IE 可用）。
- 🐛 智能限流避让：后台同步与手动操作自动错峰，不再互相抢接口。

---

## 🚀 安装方法

### 前置条件
浏览器安装 **Tampermonkey（油猴）** 扩展：
- Chrome / Edge：[Chrome 应用商店](https://chromewebstore.google.com/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
- Firefox：[Firefox 附加组件](https://addons.mozilla.org/firefox/addon/tampermonkey/)

### 安装脚本
1. 打开本仓库的 **`scau-oj-beautify.user.js`** 文件。
2. 点击右上角的 **`Raw`** 按钮，Tampermonkey 会自动弹出安装页面。
3. 点击 **「安装」** 即可。
4. 打开 OJ 首页 <https://acm.scau.edu.cn/uoj8000/mainMenu.html>，刷新即可看到新界面。

> 也可以复制 Raw 链接，在 Tampermonkey「实用工具 → 从 URL 安装」中粘贴。

---

## 📖 使用说明

- 脚本会自动匹配 `https://acm.scau.edu.cn/uoj8000/*` 下的所有页面（包括内嵌 iframe）。
- 首次进入首页时，热力图会在后台自动同步提交记录（约 1 分钟），右上角可查看进度，无需手动操作。
- 所有美化均为非侵入式，**不会影响 OJ 原有的提交、判题功能**。

---

## 🛠️ 工作原理（简述）

华农 OJ 是基于 **AppFuse + Struts 的 JSP 服务端渲染系统**，登录、判题、提交逻辑全部在服务端。
本脚本**不重写业务、不做假壳**，而是在真实页面上：
- 注入自定义 CSS 与 JavaScript 完成「换皮」；
- 通过抓取官方提交列表接口，在本地归并出热力图数据；
- 修复若干前端交互缺陷。

---

## ⚠️ 免责声明

- 本脚本仅供学习与个人使用，**与华南农业大学官方无关**。
- 脚本不会上传或收集你的账号、密码、代码等任何隐私信息。
- 请合理使用，遵守学校相关规定，不要利用本脚本进行高频请求或违规操作。

---

## 📄 开源协议

本项目基于 [MIT License](LICENSE) 开源，欢迎自由使用、修改与分享。

---

<div align="center">

如果这个脚本对你有帮助，欢迎点一个 ⭐ Star 支持！

</div>
