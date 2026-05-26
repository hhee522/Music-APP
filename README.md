# Serenity Sounds

治愈系音乐网站静态站点，包含首页、音乐库、艺人页与播放页，底部全局播放器支持播放/暂停、进度拖动与切歌，状态在页面间通过 `localStorage` 同步。

## 页面结构

| 文件 | 说明 |
|------|------|
| `index.html` | 首页 Discover：推荐、最新单曲、热门艺人 |
| `library.html` | 音乐库：歌单网格、分类筛选、播放队列侧栏 |
| `artist.html` | 艺人页：Luna Whisper 资料、热门作品、巡演 |
| `player.html` | 播放页：封面、歌词、评论、相似推荐 |
| `js/player.js` | 全局播放器逻辑（播放列表、进度、切歌） |

## 技术栈

- HTML5
- [Tailwind CSS](https://cdn.tailwindcss.com)（CDN）
- [Font Awesome 6](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css)（CDN）
- 原生 JavaScript（无构建步骤）

## 本地预览

在项目根目录启动静态服务器，例如：

```bash
# Python 3
python -m http.server 8080

# 或 Node.js（需已安装 npx）
npx serve .
```

浏览器访问：`http://localhost:8080/index.html`

> 直接双击打开 HTML 文件时，部分浏览器可能限制跨页音频或 `localStorage` 行为，建议使用本地服务器预览。

## 部署到 GitHub Pages（公开访问）

### 1. 创建仓库并推送代码

```bash
cd /path/to/ZTH
git init
git add .
git commit -m "Add Serenity Sounds static site"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git push -u origin main
```

### 2. 开启 GitHub Pages

1. 打开 GitHub 仓库 → **Settings** → **Pages**
2. **Source** 选择 **Deploy from a branch**
3. **Branch** 选 `main`，文件夹选 **`/ (root)`**
4. 保存后等待 1–3 分钟部署完成

### 3. 访问地址

- 用户/组织站点：`https://<用户名>.github.io/<仓库名>/`
- 例如仓库名为 `serenity-sounds`：  
  `https://yourname.github.io/serenity-sounds/index.html`

首页入口：`index.html`（也可在 Pages 设置中将默认文档设为 `index.html`）。

## 播放器说明

- **播放 / 暂停**：底部橙色圆形按钮
- **上一首 / 下一首**：两侧切歌按钮（播放超过 3 秒时「上一首」会回到曲首）
- **进度条**：拖动底部时间条可跳转
- **随机 / 循环**：Shuffle、Repeat 图标可切换（高亮为橙色）
- **跨页同步**：当前曲目、进度、音量保存在 `localStorage`（键名 `serenityPlayer`）
- **音频源**：演示使用 [SoundHelix](https://www.soundhelix.com/) 示例 MP3；图片使用 Unsplash / Picsum 在线链接

## 响应式

- 桌面：完整导航、多列网格、Library 页右侧 Queue 侧栏
- 平板 / 手机：折叠导航、单列/双列布局、隐藏次要控件，底部播放器保持固定

## 目录一览

```
.
├── index.html
├── library.html
├── artist.html
├── player.html
├── js/
│   └── player.js
└── README.md
```

## 许可与素材

- UI 为课程/演示用途静态实现
- 图片：Unsplash、Picsum（仅在线引用，未打包进仓库）
- 音频：SoundHelix 示例曲目（在线流式播放）

---

**Serenity Sounds** — 在音符中寻找属于你的安宁时刻。
