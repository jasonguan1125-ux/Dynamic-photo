# DynamicPhoto 📷➜🎬

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
2. 把 DynamicPhoto/ 里所有文件推上去
3. 仓库 Settings → Pages → 选 main 分支
4. 等待 2 分钟，你的网址就上线了！
```

### 方案二：Vercel（一键部署）

```
1. 安装 Vercel CLI: npm i -g vercel
2. cd DynamicPhoto && vercel --prod
3. 搞定，自动 HTTPS
```

### 方案三：Netlify

```
直接把 DynamicPhoto/ 文件夹拖到 https://app.netlify.com/drop
```

---



## 📂 文件结构

```
DynamicPhoto/
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

