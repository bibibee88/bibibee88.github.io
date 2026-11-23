# Wei Bi (闭玮) — 个人学术主页

简洁干净的静态单页主页，纯 HTML + CSS，无任何构建工具或依赖，可直接部署到 GitHub Pages。

## 内容

仅包含以下模块（锚点导航跳转）：

- Bio
- Honors and Awards
- Services
- Selected Publications/Preprints（按方向分组）
- Teaching

## 文件结构

```
webpage/
├── index.html            # 唯一页面
├── assets/
│   ├── style.css          # 自写的简洁样式
│   ├── CV_WeiBi.pdf       # 简历 PDF
│   └── photo.jpg          # 个人照片（需自行添加）
└── README.md
```

## 本地预览

```bash
cd webpage
python3 -m http.server 8080
# 浏览器访问 http://localhost:8080
```

## 待办

1. **个人照片**：放到 `assets/photo.jpg`（正方形或接近正方形）。缺失时自动隐藏，不影响页面。

## 部署到 GitHub Pages

```bash
cd webpage
git init   # 若尚未初始化
git add .
git commit -m "Clean, simple personal academic website"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git push -u origin main
```

然后在仓库 **Settings → Pages**：Source 选择 `Deploy from a branch`，Branch 选择 `main` / `/ (root)`。
