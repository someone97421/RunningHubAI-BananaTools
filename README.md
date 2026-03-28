# 🎨 RunningHub AI 图像生成器

一个基于 HTML5 的轻量级单文件 Web 应用，专为调用 **RunningHub** 平台 API 进行 AI 图像生成而设计。支持文生图和图生图两种模式自动切换，同时提供 V2 和 Pro 两种模型选择。

---

## ✨ 主要功能

### 🖼️ 双模型支持
- **V2 模型** (0.08元/张)：性价比高，适合日常使用
- **Pro 模型** (0.2-0.3元/张)：质量更优，适合专业场景
- 一键切换，实时显示价格

### 🔄 智能模式切换
- **文生图模式**：未上传图片时自动使用文字生成图像
- **图生图模式**：上传图片后自动切换为图像编辑模式
- 无需手动选择，根据输入自动判断

### 📎 多图参考支持
- 最多支持 **10 张** 参考图片（V2/Pro 模型限制）
- 支持角色一致性、风格迁移、场景融合等高级玩法

### 💡 智能引用系统
- 在提示词框中输入 `@` 即可弹出引用面板
- 快速在提示词中关联特定参考图
- 示例：`让 @img1 的人物穿上 @img2 的衣服，站在 @img3 的场景中`

### 📥 便捷图片导入
- **剪贴板粘贴** (Ctrl+V)：鼠标悬停在图片槽位上直接粘贴
- **拖拽上传**：直接拖拽图片到对应槽位
- **点击上传**：传统文件选择方式

### ⚙️ 参数自定义
- **宽高比**：支持 1:1、9:16、16:9、21:9、3:4、4:3 等多种比例
- **分辨率**：1K / 2K / 4K 三档可选
- **并发队列**：支持多任务并行，自动轮询任务状态

### 💾 配置管理
- **本地存储**：API 配置自动保存到浏览器本地
- **导入/导出**：支持 JSON 格式的配置备份与恢复
- **历史记录**：自动保存生成记录，支持预览和下载

### 🎨 界面设计
- **响应式布局**：基于 Tailwind CSS，适配桌面和移动端
- **深色/浅色主题**：一键切换，支持跟随系统
- **玻璃拟态效果**：现代感 UI 设计

---

## 🚀 快速开始

### 1. 获取 API Key

前往 [RunningHub](https://www.runninghub.cn) 注册账号并获取 API Key。

### 2. 配置应用

```
API Base URL: https://www.runninghub.cn
API Key: 你的 API Key（从 RunningHub 获取）
```

### 3. 生成图像

1. **文生图**：直接输入提示词，点击生成
2. **图生图**：先上传参考图片，再输入提示词

---

## 📋 使用说明

### 文生图
1. 在提示词框中描述你想要的图像内容
2. 选择模型（V2/Pro）、宽高比和分辨率
3. 点击"生成图像"按钮

### 图生图
1. 在左侧参考图片区域上传图片（最多10张）
2. 在提示词中使用 `@` 引用这些图片
3. 描述你想要的效果
4. 点击"生成图像"按钮

### 提示技巧
- 使用 `@img1`、`@img2` 等引用上传的图片
- Pro 模型对复杂提示词的理解能力更强
- 图生图时，参考图越多，生成效果越稳定

---

## 🔧 技术说明

### API 端点
| 模式 | V2 模型 | Pro 模型 |
|------|---------|----------|
| 文生图 | `/openapi/v2/rhart-image-n-g31-flash/text-to-image` | `/openapi/v2/rhart-image-n-pro/text-to-image` |
| 图生图 | `/openapi/v2/rhart-image-n-g31-flash/image-to-image` | `/openapi/v2/rhart-image-n-pro/edit` |

### 模型限制
| 项目 | V2 模型 | Pro 模型 |
|------|---------|----------|
| 参考图上限 | 10 张 | 10 张 |
| 单图大小 | 30 MB | 10 MB |
| 价格 | 0.08 元/张 | 0.2-0.3 元/张 |

---

## 🌐 浏览器兼容性

- Chrome / Edge / Firefox / Safari 最新版本
- 支持 PWA 安装（部分浏览器）

---

## 📄 文件说明

| 文件 | 说明 |
|------|------|
| `index.html` | 主应用文件，单文件包含所有代码 |
| `文生图文档.md` | RunningHub V2 文生图 API 文档 |
| `图生图文档.md` | RunningHub V2 图生图 API 文档 |
| `pro文生图.md` | RunningHub Pro 文生图 API 文档 |
| `pro图生图.md` | RunningHub Pro 图生图 API 文档 |

---

## ⚠️ 注意事项

1. **API Key 安全**：请勿将包含 API Key 的配置文件分享给他人
2. **本地存储**：配置和历史记录保存在浏览器本地，清除浏览器数据会丢失
3. **图片上传**：RunningHub 上传接口返回的链接有效期为 1 天
4. **费用控制**：生成前请确认模型选择，Pro 模型费用约为 V2 的 2-4 倍

---

## 📝 更新日志

### 2025-03
- ✨ 支持 RunningHub V2 和 Pro 双模型
- ✨ 自动切换文生图/图生图模式
- ✨ 新增模型价格显示
- ✨ 配置缓存改为独立名称，避免与原 Nano-Banana 冲突

---

## 🤝 致谢

- 界面设计基于 [Nano-Banana](https://github.com) 项目改进
- API 服务由 [RunningHub](https://www.runninghub.cn) 提供

---

# 🎨 RunningHub AI Image Generator

A lightweight single-file HTML5 web application for AI image generation using the **RunningHub** platform API. Supports both text-to-image and image-to-image modes with automatic switching.

---

## ✨ Key Features

- **Dual Model Support**: V2 (0.08 CNY/img) and Pro (0.2-0.3 CNY/img) models
- **Smart Mode Switching**: Automatically switches between text-to-image and image-to-image based on input
- **Multi-Image Reference**: Support up to 10 reference images
- **Smart Mention System**: Type `@` to quickly reference uploaded images
- **Clipboard Paste**: Quick image import with Ctrl+V
- **Responsive UI**: Dark/light themes with glassmorphism design

---

## 🚀 Quick Start

1. Get your API Key from [RunningHub](https://www.runninghub.cn)
2. Configure the app with your API credentials
3. Enter prompt and generate images!
