# 大学四年，想做的 100 件小事 📖

一个**可安装、可离线使用**的大学打卡手账 Web App（PWA）。
100 件小事 · 六个章节 · 心情与照片记录 · 奶油纸感手账风。

## ✨ 功能

- **100 件小事卡片墙**：10 个分类（校园时光 / 青春日常 / 朋友之间 / 一个人的浪漫 / 小小远方 / 关于热爱 / 勇敢一点 / 感受世界 / 留下痕迹 / 好好告别），支持关键词搜索 + 分类筛选
- **我的大学章节**：Lv.1 → Lv.6 章节进度线（0 / 20 / 40 / 60 / 80 / 100 件）、已珍藏件数、最近心情 Top3、大学关键词云、写给现在的自己、最近珍藏时间线
- **记录面板**：点开任意卡片即可修改状态（想去做 / 等待发生 / 已经珍藏 / 留给以后）、完成日期、心情，写一句话记录，添加照片（自动压缩到 800px）
- **数据备份**：一键导出 / 导入 JSON 备份（含照片），清空需二次确认
- **离线可用**：Service Worker 缓存，安装后断网也能打开

## 📱 安装到手机桌面

1. **Android（Chrome / Edge）**：打开网页 → 浏览器菜单 → 「添加到主屏幕 / 安装应用」
2. **iOS（Safari）**：打开网页 → 分享按钮 → 「添加到主屏幕」

安装后就是一个独立全屏的 App，和原生应用体验一致。

## 🤖 Android APK

已发布打包好的安装包：[Releases → v1.0.0](https://github.com/138849070/college-100-things/releases/tag/v1.0.0)

下载 `大学100件小事-v1.0.0.apk` 传到手机安装即可（Android 7.0+，需允许「未知来源应用」安装）。

自行重新打包：

```bash
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
# 产物：android/app/build/outputs/apk/debug/app-debug.apk
```

## 🌐 在线使用

已启用 GitHub Pages，直接访问：

```
https://138849070.github.io/college-100-things/
```

## 💾 数据说明

- 所有记录保存在**你自己设备的浏览器**里（localStorage + IndexedDB），不上传任何服务器
- 照片压缩后存在浏览器本地，替换设备或清理浏览器数据前，请先在「我的大学章节 → 数据与备份」导出 JSON 备份
- 首次打开自带 100 件小事的初始清单（含 3 条示例记录），可在备份区一键恢复初始状态

## 🗂 文件结构

```
college-100-things/
├── index.html            # 单文件应用（HTML + CSS + JS 全内联，零外部依赖）
├── manifest.webmanifest  # PWA 应用清单
├── sw.js                 # Service Worker 离线缓存
└── icons/                # 应用图标（192 / 512 / apple-touch）
```

## 🛠 技术说明

- 单文件 HTML，无任何框架、CDN、外部字体依赖，纯原生实现
- 图表（进度条、章节路线）与图标全部为内联 SVG / CSS
- 数据层：localStorage（记录）+ IndexedDB（照片），函数调用链单向，渲染互不嵌套

## License

MIT
