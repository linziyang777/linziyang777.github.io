# 林子炀 · 个人作品集

单文件静态站点。`index.html` 里内联了全部样式与脚本，图片在同级 `assets/` 目录。

## 文件

```
index.html     整站（含开场动画、四页内容、隐藏彩蛋、终章）
assets/       15 张图片，index.html 以相对路径引用
.nojekyll     告诉 GitHub Pages 不要用 Jekyll 处理
```

## 部署到 GitHub Pages

### 方式一：网页操作（不用装任何东西）

1. 打开 https://github.com/new
2. **Repository name** 填 `linziyang777.github.io`（想用根域名 `https://linziyang777.github.io/`）
   或填 `portfolio`（网址为 `https://linziyang777.github.io/portfolio/`）
3. 选 **Public**，点 **Create repository**
4. 进仓库 → **Add file** → **Upload files**
5. 把 `index.html`、`.nojekyll` 和整个 `assets` 文件夹拖进去 → **Commit changes**
6. **Settings** → 左侧 **Pages** → Source 选 `Deploy from a branch`
   → Branch 选 `main`、目录选 `/ (root)` → **Save**
7. 等 1~2 分钟，访问对应网址

### 方式二：命令行（以后更新只需两条命令）

```bash
cd liam-portfolio-github
git init
git add -A
git commit -m "init"
git branch -M main
git remote add origin https://github.com/linziyang777/linziyang777.github.io.git
git push -u origin main
```

首次 push 需要认证。GitHub 已停用账号密码，要在这里生成一个
Personal Access Token（勾 `repo` 权限）当密码用：
https://github.com/settings/tokens

### 以后更新

```bash
# 从源目录同步最新版（保留图片本地化与去注入脚本的处理）
# 然后
git add -A && git commit -m "update" && git push
```

## 注意

- GitHub Pages 免费版要求仓库 **Public**，源码对全网可见。
- 页面底部「下载简历」指向 `林子炀-个人简历.pdf`，该文件尚未放进仓库；
  要用的话把它放在 `index.html` 同级，否则按钮会 404。
- 站点用 localStorage 记录「已看过哪些页面」，用来触发地图点亮与终章印记，
  换浏览器或清缓存会重置，属正常。
