---
layout: post
title: 使用 Zola 和 GitHub Pages 构建博客
category: [zola,Github,]
tags: [zola]
---
使用 Zola 和 GitHub Pages 构建博客是一个高效且简洁的方式。Zola 是一个静态网站生成器，而 GitHub Pages 是一个免费的静态网站托管服务。以下是详细的步骤，帮助你从零开始构建并部署你的博客。


### **1. 安装 Zola**
首先，你需要在本地安装 Zola。根据你的操作系统，选择以下命令之一：

- **macOS (Homebrew):**
  ```bash
  brew install zola
  ```

- **Linux:**
  ```bash
  curl -sSL https://get.zola.dev | bash -s
  ```

- **Windows (Scoop):**
  ```bash
  scoop install zola
  ```

安装完成后，运行以下命令检查是否安装成功：
```bash
zola --version
```

---

### **2. 创建一个新的 Zola 项目**
使用 Zola 初始化一个新的博客项目：
```bash
zola init my-blog
```
这会创建一个名为 `my-blog` 的目录，并生成一个基本的 Zola 项目结构。

进入项目目录：
```bash
cd my-blog
```

---

### **3. 添加主题**
Zola 支持主题，你可以从 [Zola 主题库](https://www.getzola.org/themes/) 中选择一个喜欢的主题。以下是一个添加主题的示例：

1. 将主题添加为 Git 子模块。例如，使用 `even` 主题：
   ```bash
   git init
   git submodule add https://github.com/getzola/even.git themes/even
   ```

2. 在 `config.toml` 中启用主题：
   ```toml
   theme = "even"
   ```

3. 根据主题的文档，配置 `config.toml` 文件。例如，设置博客标题、描述等：
   ```toml
   title = "My Awesome Blog"
   description = "Welcome to my blog!"
   ```

---

### **4. 创建博客内容**
Zola 使用 Markdown 文件来生成博客内容。你可以在 `content` 目录中创建博客文章。

1. 创建博客文章：
   ```bash
   zola new content/blog/my-first-post.md
   ```

2. 编辑生成的 Markdown 文件（`content/blog/my-first-post.md`）：
   ```markdown
   +++
   title = "My First Post"
   date = 2023-10-01
   +++

   This is my first blog post using Zola!
   ```

---

### **5. 本地预览**
在本地启动 Zola 服务器，预览你的博客：
```bash
zola serve
```
打开浏览器，访问 `http://127.0.0.1:1111`，即可查看你的博客。

---

### **6. 部署到 GitHub Pages**
GitHub Pages 是一个免费的静态网站托管服务。以下是部署步骤：

#### **6.1 创建 GitHub 仓库**
1. 在 GitHub 上创建一个新的仓库，命名为 `username.github.io`（将 `username` 替换为你的 GitHub 用户名）。
2. 将本地项目与远程仓库关联：
   ```bash
   git remote add origin https://github.com/username/username.github.io.git
   ```

#### **6.2 配置 GitHub Actions**
1. 在项目根目录下创建 `.github/workflows/deploy.yml` 文件，内容如下：
   ```yaml
   name: Deploy to GitHub Pages

   on:
     push:
       branches:
         - main

   jobs:
     deploy:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout
           uses: actions/checkout@v2
           with:
             submodules: true

         - name: Setup Zola
           uses: shalzz/zola-deploy-action@v0.14.1

         - name: Deploy
           uses: peaceiris/actions-gh-pages@v3
           with:
             github_token: ${{ secrets.GITHUB_TOKEN }}
             publish_dir: ./public
   ```

2. 提交并推送代码到 GitHub：
   ```bash
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```

#### **6.3 启用 GitHub Pages**
1. 进入 GitHub 仓库的 `Settings` 页面。
2. 找到 `Pages` 选项，将 `Source` 设置为 `gh-pages` 分支。
3. 稍等片刻，GitHub Pages 会自动构建并发布你的博客。

---

### **7. 访问你的博客**
完成上述步骤后，你的博客将通过以下 URL 访问：
```
https://username.github.io
```

---

### **8. 后续维护**
- **添加新文章**：在 `content` 目录中创建新的 Markdown 文件，然后推送更改到 GitHub。
- **更新主题**：如果主题有更新，可以通过以下命令更新子模块：
  ```bash
  git submodule update --remote --merge
  ```
- **自定义博客**：根据需要修改 `config.toml` 或主题文件。

---

### **总结**
通过 Zola 和 GitHub Pages，你可以快速构建一个静态博客，并免费托管在 GitHub 上。整个过程简单高效，适合个人博客、文档站点等场景。如果你有任何问题，可以参考 [Zola 官方文档](https://www.getzola.org/documentation/) 或 [GitHub Pages 文档](https://docs.github.com/en/pages)。
