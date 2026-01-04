# 快速开始 / Quick Start

[中文](#中文说明) | [English](#english-version)

---

## 中文说明

### 🎉 您的KDD论文宣传网站已准备就绪！

这个网站基于 Vue.js 搭建，专为您的 KDD 2024 录用论文设计。

### 📋 需要做什么？

1. **安装依赖**
   ```bash
   npm install --force
   ```

2. **本地预览**
   ```bash
   npm run dev
   ```
   在浏览器打开 http://localhost:5173

3. **修改内容**
   - 阅读 `CUSTOMIZATION_CN.md` 获取详细说明
   - 主要需要修改：
     - `src/components/sections/Title.vue` - 论文标题、作者、单位
     - `src/components/mds/abstract.mdx` - 摘要
     - `src/components/mds/md.mdx` - 主要内容
     - `src/components/sections/BibTeX.vue` - 引用信息

4. **部署网站**
   - 将修改提交到 main 分支
   - GitHub Actions 自动部署
   - 网站地址: https://aster2024.github.io/swift-website/

### 📚 详细文档
- **完整中文指南**: `CUSTOMIZATION_CN.md`
- **原模板说明**: `README.md`

### ⚡ 最简单的开始方式

只需修改这3个地方：
1. `src/components/sections/Title.vue` 第10行 - 改成您的论文标题
2. `src/components/mds/abstract.mdx` - 粘贴您的论文摘要
3. `src/components/sections/BibTeX.vue` 第6-11行 - 更新引用信息

然后运行 `npm run dev` 查看效果！

---

## English Version

### 🎉 Your KDD Paper Promotional Website is Ready!

This Vue.js-based website is customized for your KDD 2024 accepted paper.

### 📋 What to Do?

1. **Install Dependencies**
   ```bash
   npm install --force
   ```

2. **Local Preview**
   ```bash
   npm run dev
   ```
   Open http://localhost:5173 in your browser

3. **Customize Content**
   - Read `CUSTOMIZATION.md` for detailed instructions
   - Main files to edit:
     - `src/components/sections/Title.vue` - Paper title, authors, affiliations
     - `src/components/mds/abstract.mdx` - Abstract
     - `src/components/mds/md.mdx` - Main content
     - `src/components/sections/BibTeX.vue` - Citation

4. **Deploy Website**
   - Commit changes to main branch
   - GitHub Actions auto-deploys
   - Live at: https://aster2024.github.io/swift-website/

### 📚 Documentation
- **Full English Guide**: `CUSTOMIZATION.md`
- **Original Template**: `README.md`

### ⚡ Simplest Way to Start

Just modify these 3 places:
1. `src/components/sections/Title.vue` line 10 - Your paper title
2. `src/components/mds/abstract.mdx` - Paste your abstract
3. `src/components/sections/BibTeX.vue` lines 6-11 - Update citation

Then run `npm run dev` to see the result!

---

## 🚀 Deployment Status

- ✅ Vite configuration for GitHub Pages
- ✅ KDD 2024 template content
- ✅ Placeholder content ready for customization
- ✅ Build process verified
- ✅ GitHub Actions workflow configured
- ✅ Security checked (no vulnerabilities)

## 📁 Repository Structure

```
swift-website/
├── public/                  # Static assets (images, icons, etc.)
├── src/
│   ├── components/
│   │   ├── sections/       # Page sections (Title, Abstract, etc.)
│   │   └── mds/           # Markdown content files
│   └── main.js
├── CUSTOMIZATION.md         # English guide
├── CUSTOMIZATION_CN.md      # Chinese guide
├── README.md               # Original template docs
└── QUICKSTART.md           # This file
```

## 🎯 Support

Having issues? Check:
1. Node.js version >= 18
2. Run `npm install --force` if dependencies fail
3. Read the customization guides for details

Good luck with your KDD 2024 paper! 🎉
