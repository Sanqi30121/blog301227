# 三七的博客

这是一个纯静态博客仓库，无需 Node.js、npm 或构建命令，可直接部署到 GitHub + Cloudflare Pages。

## 目录

```text
.
├─ index.html
├─ assets/
│  ├─ css/style.css
│  └─ js/app.js
└─ content/
   ├─ site.json
   ├─ articles/
   │  ├─ index.json
   │  └─ example/article.html
   ├─ albums/
   │  ├─ index.json
   │  └─ example/
   │     ├─ album.json
   │     └─ images/example-photo.svg
   ├─ moments/moments.json
   └─ links/links.json
```

## 长期管理

- 网站名称、首页介绍、关于页：首页的“主页 / GitHub / Email”显示项都在 `content/site.json`；默认保留原位置，但 `url` 留空，由你自己填写
- 新文章：复制 `content/articles/example/`，修改正文文件，再向 `content/articles/index.json` 添加一条记录
- 新相册：复制 `content/albums/example/`，把照片放进该相册自己的 `images/`，修改 `album.json`，再向 `content/albums/index.json` 添加一条记录
- 新动态：编辑 `content/moments/moments.json`
- 链接/友链：编辑 `content/links/links.json`；当前默认是空数组，不包含任何外部链接
- 页面样式：`assets/css/style.css`
- 页面功能：`assets/js/app.js`

## Cloudflare Pages

这是纯静态项目：不需要构建命令。部署时将输出目录设置为仓库根目录即可。

> 注意：因为内容通过 `fetch()` 读取 JSON/HTML，本地不要直接双击 `index.html` 预览；应通过本地静态服务器或部署后的网址访问。
