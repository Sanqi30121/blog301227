# 三七的博客

这是一个纯静态博客仓库，无需 Node.js、npm 或构建命令，可直接部署到 GitHub + Cloudflare Pages。

## 目录

```text
.
├─ index.html
├─ README.md
├─ assets/
│  ├─ css/style.css
│  └─ js/app.js
└─ content/
   ├─ site.json
   ├─ images/
   │  └─ avatar.jpg
   ├─ articles/
   │  ├─ index.json
   │  └─ example/
   │     ├─ article.html
   │     └─ images/example-image.svg
   ├─ albums/
   │  ├─ index.json
   │  └─ example/
   │     ├─ album.json
   │     └─ images/example-photo.svg
   ├─ moments/moments.json
   └─ links/links.json
```

## 长期管理

- 网站名称、首页介绍、关于页、首页的“主页 / GitHub / Email”显示项：`content/site.json`。三个链接默认只保留显示位置，`url` 留空，由你自己填写。
- 头像：`content/images/avatar.jpg`。首页和“关于”页面共用这一张图片；以后直接替换同名文件即可。
- 新文章：复制 `content/articles/example/`，文章自己的图片放到该文章目录的 `images/`，修改 `article.html`，再向 `content/articles/index.json` 添加一条记录。
- 新相册：复制 `content/albums/example/`，把照片放进该相册自己的 `images/`，修改 `album.json`，再向 `content/albums/index.json` 添加一条记录。
- 新动态：编辑 `content/moments/moments.json`。
- 链接/友链：编辑 `content/links/links.json`；当前默认是空数组，不包含任何外部链接。
- 页面样式：`assets/css/blog-20261004.css`。
- 页面功能：`assets/js/blog-20261004.js`。正常管理内容时不需要修改它。

## 手机端与相册交互

- 手机端顶部导航为单行：左侧博客名称，右侧搜索与三横线菜单。主页 / 文章 / 相册 / 动态 / 链接 / 关于以及夜间模式都在右侧抽屉菜单中。
- 手机端照片大图支持左右滑动：左滑下一张，右滑上一张；左右按钮仍然保留。
- 手机端照片大图采用“上方照片 + 下方说明”布局，说明较长时可在说明区域内上下滚动。
- 电脑端照片大图采用“左侧照片 + 右侧说明”布局，长说明只在右侧说明栏滚动，不影响照片尺寸。
- 照片说明仍然只需要写在对应相册的 `album.json` 的 `text` 字段中，不需要分别维护手机和电脑两份内容。

## 搜索

搜索会在第一次使用时读取文章正文和相册照片说明，因此可以搜索文章标题、简介、正文、相册、照片说明、动态和你以后添加的链接。第一次搜索可能比后续搜索稍慢一点，这是正常现象。

## Cloudflare Pages

这是纯静态项目，不需要构建命令。部署时使用仓库根目录作为静态站点内容即可。

> 注意：因为内容通过 `fetch()` 读取 JSON/HTML，本地不要直接双击 `index.html` 预览；应通过本地静态服务器或部署后的网址访问。

## 更换头像

首页和“关于”页面共用：

```text
content/images/avatar.jpg
```

以后更换头像时，直接用新的 JPG 照片替换这个文件，并保持文件名仍然是 `avatar.jpg`。不需要修改代码或 JSON。建议使用正方形图片，例如 800×800 或 1200×1200，页面会自动裁切为圆形。
