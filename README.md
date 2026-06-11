# Motion2MP4 📷➜🎬

**手机动态照片 → MP4 视频 · 纯浏览器处理 · 不上传服务器**

一个免费、隐私安全的在线工具，支持：
- 🍎 **iPhone 实况照片** (`.HEIC` + `.MOV` → `.mp4`)
- 📱 **小米动态照片** (`MVIMG_.jpg` → `.mp4`)
- 🤖 **Android 动态照片** (含嵌入视频的 `.jpg` → `.mp4`)

---

## 🚀 快速部署（免费零成本）

### 方案一：GitHub Pages（推荐）

```
1. 在 GitHub 创建新仓库
2. 把 motion2mp4/ 里所有文件推上去
3. 仓库 Settings → Pages → 选 main 分支
4. 等待 2 分钟，你的网址就上线了！
```

### 方案二：Vercel（一键部署）

```
1. 安装 Vercel CLI: npm i -g vercel
2. cd motion2mp4 && vercel --prod
3. 搞定，自动 HTTPS
```

### 方案三：Netlify

```
直接把 motion2mp4/ 文件夹拖到 https://app.netlify.com/drop
```

---

## 💰 盈利方案

### 1. 广告收入（推荐入门）
在 `index.html` 中合适位置添加：
- **Google AdSense** — 等流量上来后自动展示广告
- 建议位置：转换列表下方、footer 上方
- 预期：日活 500+ 时月收入 $50-200

### 2. 打赏赞助（已内置）
页面底部已有"请喝咖啡"按钮，用户可自定义：
- 替换为 **微信收款码** 或 **支付宝收款码**
- 添加 **爱发电** (afdian.com) 链接
- 添加 **Buy Me a Coffee** (buymeacoffee.com)

### 3. 增值功能（Freemium 模式）
免费版 → 付费 Pro 版功能建议：

| 功能 | 免费 | Pro |
|------|------|-----|
| 单次文件数 | ≤10 | 不限 |
| 批量下载 | ZIP 逐个 | 一键 ZIP |
| 视频质量 | 原始 | 可选压缩 |
| 转 GIF | ❌ | ✅ |

Pro 版可通过以下方式实现：
- 另建 `pro.html` 页面
- 使用 Stripe / 微信支付 API 验证
- 或简单用爱发电赞助后发 Pro 访问码

### 4. SEO 获客
在 `index.html` `<head>` 中已预埋 SEO 标签：
- 标题关键词：`手机动态照片转MP4` `Live Photo转视频`
- 建议到知乎、小红书发布教程帖引流
- 搜索流量词：`小米动态照片转MP4` `iPhone实况照片转视频` `MVIMG转MP4`

---

## 📂 文件结构

```
motion2mp4/
├── index.html      # 主页面（全部 UI + 转换引擎）
├── manifest.json   # PWA 配置（可安装到手机/桌面）
└── sw.js           # 离线缓存服务
```

就这么 3 个文件，零依赖，托管在任何静态服务器上就能跑。

---

## 🔒 隐私说明

所有文件处理 100% 在浏览器本地完成，没有任何数据上传到服务器。
你可以断网使用（PWA 缓存后）。

---

## 🔧 技术原理

- **iPhone Live Photo**: 读取 MOV 文件的 `ftyp` box，将 `qt  ` 品牌标识改为 `mp42`，重新封装为标准 MP4
- **Android Motion Photo**: 在 JPEG 文件中搜索 `ftyp` magic bytes，定位嵌入的 MP4 数据起始位置并提取
- 纯 JavaScript + File API，无需任何后端

---

## 📈 推广建议

1. 发布到 **小众软件** / **知乎** / **小红书** 等平台
2. 视频教程："手机动态照片怎么转成视频？在线免费工具"
3. 在 GitHub 加话题标签：`#livephoto` `#motionphoto` `#converter`
4. 在 Product Hunt 提交
