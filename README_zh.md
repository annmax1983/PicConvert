# PicConvert

一款轻量级浏览器扩展，可在本地将图片转换为 PNG、JPG、WEBP 和 AVIF 格式 —— 完全本地处理，零数据上传。

> 基于 Chromium · Manifest V3 · 零追踪 · 100% 浏览器内处理

[English](README.md) | 中文 | [Español](README_es.md) | [Deutsch](README_de.md) | [日本語](README_ja.md) | [Français](README_fr.md)

---

## 为什么选择 PicConvert？

大多数图片转换工具需要将文件上传到远程服务器。PicConvert 使用 Canvas API 在浏览器内完成所有处理 —— 数据永远不会离开你的设备。

| 优势 | 说明 |
|------|------|
| 🔒 **100% 隐私** | 所有处理在浏览器内存中完成，无服务器、无上传、无追踪 |
| ⚡ **即时转换** | ≤5MB 图片转换时间低于 500ms，无需等待服务器往返 |
| 🎯 **零依赖** | 使用原生 JavaScript 和 Chrome API 构建，无框架、无冗余 |
| 🌍 **6 种语言** | 自动检测浏览器语言 —— 英文、西班牙文、德文、日文、法文、中文 |
| 📋 **复制与保存** | 右键图片可保存为文件或直接复制到剪贴板 |
| 📁 **拖拽转换** | 将本地图片拖放到弹窗即可快速转换 |

---

## 功能特性

| 功能 | 说明 |
|------|------|
| 🖼️ **4 种格式** | 转换为 PNG（无损）、JPG（高质量）、WEBP（紧凑）或 AVIF（最佳压缩） |
| 📋 **复制到剪贴板** | 右键 → 复制为 PNG/JPG/WEBP/AVIF —— 直接粘贴到邮件、聊天、文档 |
| 📊 **文件大小对比** | Toast 通知显示原始大小 vs 转换后大小及节省百分比 |
| 🎚️ **可调质量** | 通过弹窗滑块微调 JPG、WEBP、AVIF 的导出质量 |
| 🔗 **智能链接清洗** | 剥离 CDN 追踪参数（`w=`、`h=`、`format=`、`watermark=` 等）以获取原始图片 |
| 📁 **拖拽转换** | 将本地图片文件拖放到弹窗即可转换，无需右键 |
| 🌐 **跨域支持** | 通过 Service Worker 从任意网站获取图片 —— 绕过 CORS 和画布污染问题 |
| 🔤 **6 语言国际化** | 右键菜单和界面自动匹配浏览器语言（EN/ES/DE/JA/FR/ZH-CN） |
| 🛡️ **JPG 白底填充** | PNG 转 JPG 时自动用白色填充透明背景 |
| ⏱️ **重复点击拦截** | 2 秒内对同一图片的重复操作自动忽略 |
| 📦 **大图处理** | >20MB 图片显示异步处理指示器，不会冻结界面 |

---

## 预览

<!-- 替换为实际截图 -->
<p align="center">
  <img src="assets/popup.png" alt="PicConvert 弹窗" width="360">
</p>

<p align="center">
  <img src="assets/context-menu.png" alt="PicConvert 右键菜单">
</p>

---

## 支持的浏览器

| 浏览器 | 状态 |
|--------|------|
| Google Chrome | ✅ 完全支持 |
| Microsoft Edge | ✅ 完全支持 |
| Brave | ✅ 支持 |
| Opera | ✅ 支持 |
| Vivaldi | ✅ 支持 |
| 任意 Chromium 内核浏览器 | ✅ 支持（Manifest V3） |

---

## 安装

### 从源码安装（开发者模式）

1. 打开浏览器扩展页面：
   - **Chrome**：`chrome://extensions/`
   - **Edge**：`edge://extensions/`
2. 启用**开发者模式**（右上角开关）
3. 点击**加载已解压的扩展程序**，选择 `pic-convert` 文件夹
4. 工具栏将出现 ✨ PicConvert 图标

---

## 使用方法

### 右键转换

1. 在网页上右键点击任意图片
2. 从上下文菜单中选择 **PicConvert**
3. 选择**另存为**或**复制为**
4. 选择格式：PNG、JPG、WEBP 或 AVIF
5. 完成 —— 文件立即下载，或图片已复制到剪贴板

### 拖拽转换

1. 点击工具栏中的 PicConvert 图标打开弹窗
2. 将本地图片文件拖放到拖拽区域
3. 选择目标格式
4. 转换后的文件自动下载

### 质量设置

打开弹窗，使用滑块调整 JPG、WEBP 和 AVIF 的导出质量。PNG 始终无损。设置自动保存。

---

## 右键菜单结构

```
PicConvert
├── 另存为 PNG（无损）
├── 另存为 JPG（高质量）
├── 另存为 WEBP（紧凑）
├── 另存为 AVIF（最佳压缩）
├── 复制为 PNG（无损）
├── 复制为 JPG（高质量）
├── 复制为 WEBP（紧凑）
└── 复制为 AVIF（最佳压缩）
```

**复制为**和**另存为**菜单仅在右键点击图片或指向图片文件的链接时显示（`.png`、`.jpg`、`.jpeg`、`.webp`、`.avif`、`.gif`、`.bmp`、`.jfif`、`.svg`）。

---

## 隐私

PicConvert 以隐私为核心原则：

- ✅ **零数据上传** —— 所有图片处理在浏览器内存中完成
- ✅ **无分析** —— 无追踪、无遥测、无远程调用
- ✅ **无 Cookie** —— 不读取或写入浏览器 Cookie
- ✅ **无浏览历史** —— 不访问浏览数据
- ✅ **仅临时内存** —— 图片在转换期间存在于内存中，完成后立即销毁
- ✅ **最小权限** —— 仅请求必要权限：`contextMenus`、`downloads`、`offscreen`、`storage`、`clipboardWrite`

---

## 工作原理

```
右键点击图片
       ↓
Service Worker 获取图片 Blob（绕过 CORS）
       ↓
将 Blob 发送到离屏文档（具有 Canvas 访问权限的隐藏 DOM）
       ↓
Canvas 以原始分辨率绘制图片
       ↓
以指定质量导出为目标格式
       ↓
返回数据 URL → 触发下载或复制到剪贴板
       ↓
销毁所有临时资源（Blob、Canvas、图片元素）
```

> **为什么使用离屏？** Chrome 的 Manifest V3 将后台作为 Service Worker 运行，没有 DOM 访问权限。Canvas API 需要 DOM，因此我们使用 Chrome 的 Offscreen API 创建隐藏文档进行图片处理。

---

## 导出质量默认值

| 格式 | 质量 | 说明 |
|------|------|------|
| PNG | 无损 | 无质量设置 —— 始终保持完整质量和透明度 |
| JPG | 92 | 高质量，大小和清晰度的良好平衡 |
| WEBP | 90 | 现代格式，同等质量下比 JPG 小约 25-35% |
| AVIF | 70 | 下一代格式，比 WEBP 小约 20-30%，最适合 Web 传输 |

所有质量值均可通过弹窗滑块调整（范围：10–100）。

---

## 许可

Copyright © 2026 PicConvert. 保留所有权利。

---

## ❤️ 支持

如果你觉得 PicConvert 有用，欢迎支持项目！

<!-- 在此添加支持链接 -->
**[👉 支持 PicConvert](https://www.creem.io/payment/prod_4LTHdgvsMSURUjevX47qHE)**

---

> **注意：** 所有核心转换功能将始终保持免费，无任何限制。
