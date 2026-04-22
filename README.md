# 🎨 RunningHub AI 图像生成器

一个轻量级的 Web 应用，用于调用 **RunningHub** 平台 API 进行 AI 图像生成。支持多种模型，文生图和图生图自动切换，界面简洁易用。

---

## ✨ 主要功能

### 🧠 多模型切换
- **NanoBanana**：RunningHub 自研模型，性价比高
  - **V2 模型** (1k/2k 0.16元/张, 4k 0.2元/张)：日常使用首选
  - **Pro 模型** (1k/2k 0.4元/张, 4k 0.5元/张)：更高质量，适合专业场景
- **GPT-image2**：OpenAI 全能图片模型，支持文生图和图生图
- 点击标签页即可一键切换模型，各自参数独立保存

### 🔄 智能模式切换
- **文生图模式**：未上传图片时，自动用文字生成图像
- **图生图模式**：上传参考图片后，自动切换为图像编辑模式
- 无需手动选择，根据输入自动判断

### 📎 多图参考支持
- 最多支持 **10 张** 参考图片
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
- **分辨率** (NanoBanana)：1K / 2K / 4K 三档可选
- **并发队列**：支持多任务并行，自动轮询任务状态

### 💾 配置与历史
- **本地存储**：API 配置和模型参数自动保存到浏览器
- **导入/导出**：支持 JSON 格式的配置备份与恢复
- **历史记录**：自动保存生成记录，支持预览、复用和下载

### ✂️ 内置裁图工具
- 支持网格切割图片（2×2、3×3、4×4 等多种规格）
- 切割后可单张下载或打包下载全部切片

### 🎨 界面设计
- **响应式布局**：适配桌面和移动端
- **深色/浅色主题**：一键切换，支持跟随系统

---

## 🚀 快速开始

### 1. 获取 API Key

前往 [RunningHub](https://www.runninghub.cn) 注册账号并获取 API Key。

### 2. 配置应用

在页面上方的"设置与配置"区域填写：

```
API Base URL: https://www.runninghub.cn
API Key: 你的 API Key（从 RunningHub 获取）
```

### 3. 生成图像

1. **选择模型**：在提示词输入区右上角切换 NanoBanana 或 GPT-image2
2. **文生图**：直接输入提示词，点击生成
3. **图生图**：先上传参考图片，再输入提示词

---

## 📋 使用说明

### 切换模型
在提示词输入区的右上角，点击标签页切换：
- **NanoBanana**：RunningHub 自研模型，提供 V2 和 Pro 两种子模型选择
- **GPT-image2**：全能图片模型，图生图时需要至少上传一张参考图

切换后，下方的参数选项会自动变化，各模型的参数设置独立保存。

### 文生图
1. 选择想要的模型（NanoBanana 或 GPT-image2）
2. 在提示词框中描述你想要的图像内容
3. 根据需要调整宽高比、分辨率等参数
4. 点击"生成图像"按钮

### 图生图
1. 在左侧参考图片区域上传图片（最多10张）
2. 在提示词中使用 `@` 引用这些图片
3. 描述你想要的效果
4. 点击"生成图像"按钮

### 提示技巧
- 使用 `@img1`、`@img2` 等引用上传的图片
- Pro 模型对复杂提示词的理解能力更强
- 图生图时，参考图越多，生成效果越稳定
- 提示词支持直接粘贴纯文本，避免富文本格式干扰

### 复用历史记录
- 点击历史记录图片上的"复用"按钮，可一键恢复当时的提示词和参考图
- 参考图会以 Base64 形式保存到本地，复用时自动还原

---

## ⚠️ 注意事项

1. **API Key 安全**：请勿将包含 API Key 的配置文件分享给他人
2. **本地存储**：配置和历史记录保存在浏览器本地，清除浏览器数据会丢失
3. **图片链接有效期**：生成结果图片链接有效期为 24 小时，请及时下载保存
4. **费用控制**：生成前请确认模型选择，不同模型和分辨率价格不同
5. **GPT-image2 图生图**：必须至少上传一张参考图才会进入图生图模式

---

## 📝 更新日志

### 2026-04
- ✨ 新增 GPT-image2 模型支持，文生图/图生图均可使用
- ✨ 模型切换改为标签页形式，体验更直观
- ✨ 各模型参数独立保存，切换后自动恢复
- 💰 更新 V2 和 Pro 模型价格

### 2025-03
- ✨ 支持 RunningHub V2 和 Pro 双模型
- ✨ 自动切换文生图/图生图模式
- ✨ 新增模型价格显示

---

## 🤝 致谢

- API 服务由 [RunningHub](https://www.runninghub.cn) 提供

---

# 🎨 RunningHub AI Image Generator

A lightweight web application for AI image generation using the **RunningHub** platform API. Supports multiple models with automatic text-to-image and image-to-image switching.

---

## ✨ Key Features

- **Multi-Model Support**: NanoBanana (V2/Pro) and GPT-image2
- **Smart Mode Switching**: Automatically switches between text-to-image and image-to-image
- **Multi-Image Reference**: Support up to 10 reference images
- **Smart Mention System**: Type `@` to quickly reference uploaded images
- **Clipboard Paste**: Quick image import with Ctrl+V
- **Built-in Crop Tool**: Grid-based image splitting with batch download
- **Responsive UI**: Dark/light themes

---

## 🚀 Quick Start

1. Get your API Key from [RunningHub](https://www.runninghub.cn)
2. Configure the app in the Settings panel
3. Select a model and generate images!
