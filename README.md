# Wei Bi (闭玮) — 个人学术主页

基于纯 HTML / CSS / JS 搭建的个人学术主页，无需构建工具，可直接部署到 GitHub Pages。

## 目录结构

```
webpage/
├── index.html          # 首页：About / 研究方向 / 教育与工作经历 / Featured Projects / 荣誉奖项 / 精选论文 / 基金与教学 / 联系方式
├── publications.html   # 完整发表列表（88 篇，按年份分组）
├── style.css            # 全站样式
├── script.js             # 移动端导航、滚动高亮、页脚年份等交互
├── assets/
│   ├── CV_WeiBi.pdf     # 简历 PDF（首页「CV」按钮可下载）
│   └── photo.jpg         # 个人照片（需自行添加，见下文）
└── README.md
```

## 本地预览

无需安装任何依赖，直接用浏览器打开 `index.html`，或者在本目录下起一个本地静态服务器：

```bash
cd webpage
python3 -m http.server 8080
# 浏览器访问 http://localhost:8080
```

## 待办 / 需要你补充的内容

1. **个人照片**：把一张照片放到 `assets/photo.jpg`（建议正方形，≥400×400px）。未放置照片前，首页会自动显示圆角色块 + 姓名缩写 "WB" 作为占位。
2. **外部链接**：`index.html` 中的 Google Scholar / GitHub / DBLP 链接目前是占位地址（`#` 或平台首页），请替换为你本人的真实主页链接。
3. **电话号码**：出于隐私考虑，网站上默认只展示邮箱，未展示 CV 中的手机号码。如需展示请自行在 `index.html` 的 `.contact-row` 中添加。
4. **到岗后更新**：目前首页用 "Incoming Associate Professor" 徽章标注"即将入职"。正式入职后，建议：
   - 去掉 `badge-incoming` 徽章或改为到岗日期说明；
   - 补充南方科技大学人工智能学院的实验室名称、办公室地址、招生方向等信息；
   - 如有官方照片 / 学院模板要求，可据此替换样式。

## 部署到 GitHub Pages

1. 在 GitHub 上新建一个仓库，推荐命名为 `<你的 GitHub 用户名>.github.io`（这样访问地址就是 `https://<用户名>.github.io/`），或任意仓库名（访问地址则是 `https://<用户名>.github.io/<仓库名>/`）。
2. 在本目录下执行：

   ```bash
   cd webpage
   git init
   git add .
   git commit -m "Initial personal academic website"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git push -u origin main
   ```

3. 打开 GitHub 仓库页面 → **Settings → Pages**：
   - Source 选择 `Deploy from a branch`
   - Branch 选择 `main`，目录选择 `/ (root)`
   - 保存后等待 1–2 分钟，页面顶部会出现访问地址。

4. （可选）如果想绑定自己的域名，在仓库根目录新建 `CNAME` 文件，写入你的域名，并在域名服务商处配置 DNS 指向 GitHub Pages。

## 更新内容

- 日常更新论文、项目等内容，直接编辑 `index.html` / `publications.html` 对应区块即可，无需重新构建。
- 修改后提交并推送到 `main` 分支，GitHub Pages 会在约 1 分钟内自动更新。
