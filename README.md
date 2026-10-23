# Wei Bi (闭玮) — 个人学术主页

参照 [peilinzhao.github.io](https://peilinzhao.github.io/) 的极简学术主页风格（Jekyll `minima` 主题）重建：
纯静态 HTML + 原版 minima CSS，无需任何构建工具或依赖，可直接部署到 GitHub Pages。

## 页面结构（对照模版的 5 个导航页）

| 文件 | 对应导航 | 内容 |
|---|---|---|
| `index.html` | About Me | 身份信息、Links、Notice（招生启事）、BIO、Working/Education Experiences、Honors and Awards、Services、Research Grants |
| `research.html` | Research | 研究方向分类介绍 |
| `projects.html` | Projects | Featured Projects P1–P8（模版没有此页，因内容丰富单独新增一页） |
| `publications.html` | Publications | 完整 88 篇论文，按年份倒序排列的扁平列表（与模版发表列表格式一致） |
| `teaching.html` | Teaching | 教学经历 |

```
webpage/
├── index.html
├── research.html
├── projects.html
├── publications.html
├── teaching.html
├── assets/
│   ├── main.css          # 直接采用 minima 主题原版 CSS + 少量自定义补充（文末注明）
│   ├── CV_WeiBi.pdf       # 简历 PDF（首页 Links 中 "CV" 可下载）
│   └── photo.jpg          # 个人照片（需自行添加，见下文）
└── README.md
```

## 本地预览

```bash
cd webpage
python3 -m http.server 8080
# 浏览器访问 http://localhost:8080
```

## 待办 / 需要你补充的内容

1. **个人照片**：放到 `assets/photo.jpg`（正方形或接近正方形，建议 ≥400×400px）。放置前首页不会显示破损图标（已做 `onerror` 容错，照片缺失时自动隐藏）。
2. **外部链接**：`index.html` 的 Google Scholar / DBLP / GitHub 链接目前是平台首页占位，请替换为你本人的真实主页链接。
3. **电话号码**：出于隐私考虑未展示，仅保留邮箱。
4. **正式入职后**：可以精简或去掉首页 Notice 中"即将入职"的措辞，并在 Teaching 页补充具体开课信息。

## 部署到 GitHub Pages

```bash
cd webpage
git init   # 若尚未初始化
git add .
git commit -m "Personal academic website (minima-style)"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git push -u origin main
```

然后在仓库 **Settings → Pages**：Source 选择 `Deploy from a branch`，Branch 选择 `main` / `/ (root)`，保存后等待约 1 分钟即可访问。

> 注：本项目是纯静态 HTML（未使用真正的 Jekyll 构建），因此无需 `_config.yml` / Gemfile，GitHub Pages 会直接原样托管这些文件，构建更快、部署更稳定；视觉效果与原版 minima 主题一致。

## 更新内容

直接编辑对应的 `.html` 文件即可，保存后推送到 `main` 分支，GitHub Pages 会在约 1 分钟内自动更新。
