# NoviDesk 官方主页文档工程

本目录是一个**标准 GitHub Pages（Jekyll）文档工程**，用于发布 NoviDesk 桌面工作站的官方推广主页。
结构参考同组织的 `NoviDesk-Privacy` 仓库（独立仓库、`main` 分支、仓库根目录即 Pages 源）。

## 目录结构

```
Docs/Docs/
├── _config.yml              # Jekyll / GitHub Pages 配置（站点标题、语言、无第三方主题）
├── _layouts/
│   └── default.html         # 页面骨架（引用样式、页脚）
├── assets/
│   ├── css/
│   │   └── style.css         # 中英双语排版样式 + 深/浅色自适应
│   └── img/
│       └── 0X-*.svg          # 各节插图（矢量，可直接替换为真实截图 .png/.jpg）
├── index.md                 # 【主页内容】双语推广文案，日常只改这个文件
└── README.md               # 本说明
```

## 如何编辑（便于修改）

- **改文字**：只编辑 `index.md`，按 Markdown 书写；中英文分别用 `.zh` / `.en` 样式类包裹。
- **换插图**：把 `assets/img/` 下对应 `.svg` 换成真实截图（同名 `.png`/`.jpg` 亦可，同步改 `index.md` 里的引用路径）。
- **调样式**：改 `assets/css/style.css`。

## 如何发布到 GitHub Pages

```bash
# 1) 在本目录初始化仓库（若尚未初始化）
git init -b main
git add .
git commit -m "Add NoviDesk homepage"

# 2) 关联远程仓库（建议命名 NoviDesk-Docs，与 NoviDesk-Privacy 同组织）
git remote add origin https://github.com/tech-littlesoft/NoviDesk-Docs.git

# 3) 推送 main 分支，GitHub Pages 自动构建发布
git push -u origin main
```

> 仓库设置 → Pages → Source 选择 **main 分支 / root** 即可。
> 无需本地安装 Jekyll：GitHub 会在服务端自动用 `_config.yml` 构建。

## 本地预览（可选）

如需本地预览，安装 Ruby + Jekyll 后在本目录执行：

```bash
bundle init        # 生成 Gemfile 后加入 gem "github-pages"
bundle exec jekyll serve
```
