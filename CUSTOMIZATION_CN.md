# KDD论文宣传网站 - 定制指南

这个网站已经为您的KDD 2024录用论文定制好了基础框架。请按照本指南更新为您的实际论文信息。

## 快速开始

1. **安装依赖**:
   ```bash
   npm install --force
   ```

2. **运行开发服务器**:
   ```bash
   npm run dev
   ```
   然后在浏览器中打开 http://localhost:5173 查看网站

3. **构建生产版本**:
   ```bash
   npm run build
   ```

## 需要定制的文件

### 1. 标题和基本信息
**文件**: `src/components/sections/Title.vue`

修改以下变量：

```javascript
// 论文标题
const title = 'Your KDD Paper Title Here'  // 改为您的实际标题

// 作者列表 - 根据需要添加/删除
const authors = [
  {
    name: "作者姓名1",                    // 您的真实姓名
    icon: "./icon/author1.jpg",         // 您的照片（放到 public/icon/ 目录）
    homepage: "https://yourwebsite.com/", // 您的个人主页
    address_flag: "1,*"                  // 机构编号和符号
  },
  // 添加更多作者...
]

// 机构列表
const addresses = [
  {
    address_flag: "1",
    name: "您的大学",                     // 您的机构名称
    icon: "./icon/university.png",      // 机构logo（放到 public/icon/）
    homepage: "https://www.youruniversity.edu"  // 机构网址
  },
  // 添加更多机构...
]

// 资源链接 - 当链接可用时设置 disabled: false
const buttons = [
  {
    disabled: false,  // 有链接时设为 false
    name: "Paper",
    link: "https://arxiv.org/abs/your-paper-id",  // 改为实际论文链接
    component: Document,
  },
  {
    disabled: false,
    name: "Code",
    link: "https://github.com/yourusername/your-repo",  // 改为实际代码仓库
    component: Files,
  },
  // 根据需要更新其他按钮
]
```

### 2. 摘要
**文件**: `src/components/mds/abstract.mdx`

将占位符文本替换为您的实际论文摘要。

### 3. 主要内容
**文件**: `src/components/mds/md.mdx`

这个文件包含宣传页面的主要内容。更新为：
- 研究介绍
- 主要贡献
- 方法概述
- 结果和性能对比
- 结论

支持的Markdown语法：
- 标题 (`#`, `##`, `###`)
- 列表（有序和无序）
- 表格
- 链接
- 图片
- LaTeX公式（使用 `$$...$$`）
- 代码块

### 4. BibTeX引用
**文件**: `src/components/sections/BibTeX.vue`

更新为您的实际论文信息：

```javascript
bibtex: [
  "@inproceedings{yourname2024yourtitle,",
  "    title={您的论文标题},",
  "    author={第一作者 and 第二作者},",
  "    booktitle={Proceedings of the 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining},",
  "    year={2024},",
  "    organization={ACM}",
  "}",
]
```

### 5. 页面元数据
**文件**: `index.html`

更新页面标题和元标签：

```html
<meta name="keywords" content="KDD, KDD 2024, 您的关键词">
<meta name="description" content="您的论文简短描述">
<title>您的论文标题 - KDD 2024</title>
```

### 6. Logo
**文件**: `public/logo.png`

替换为您的项目logo或保持原样。在 `Title.vue` 中引用：
```javascript
const logo = './logo.png'  // 设为 '' 可隐藏logo
```

### 7. 作者照片
**目录**: `public/icon/`

将作者照片添加到此目录，并在 `Title.vue` 中引用。

## 添加媒体内容

### 图片
将图片放在 `public/` 目录，在 `.mdx` 文件中引用：
```markdown
![替代文本](./your-image.png)
```

### 视频
编辑 `src/components/sections/Video.vue` 添加视频（本地、YouTube或B站）。

### 图片轮播
编辑 `src/components/sections/Carousel.vue` 添加图片轮播。

### 图表
编辑 `src/components/sections/Echart.vue` 添加交互式图表。

## GitHub Pages部署

网站已配置为部署到 `https://aster2024.github.io/swift-website/`

仓库已设置GitHub Actions，当您推送更改时会自动构建和部署。

### 部署步骤：
1. 在本地进行定制
2. 用 `npm run dev` 测试
3. 用 `npm run build` 验证无错误
4. 提交并推送您的更改
5. GitHub Actions会自动部署到 `gh-pages` 分支
6. 您的网站将在 `https://aster2024.github.io/swift-website/` 上线

## 定制组件

网站包含许多可选组件，可在 `src/components/Main.vue` 中显示/隐藏：

```vue
<template>
  <Title/>           <!-- 始终保留 -->
  <Carousel/>        <!-- 不需要可删除 -->
  <Video/>           <!-- 不需要可删除 -->
  <Abstract/>        <!-- 始终保留 -->
  <Markdown/>        <!-- 始终保留 -->
  <Latex/>           <!-- 不需要可删除 -->
  <Table/>           <!-- 不需要可删除 -->
  <Collapse/>        <!-- 不需要可删除 -->
  <Echart/>          <!-- 不需要可删除 -->
  <!-- ... 更多组件 ... -->
  <BibTeX/>          <!-- 始终保留 -->
  <Comment/>         <!-- 不需要可删除 -->
</template>
```

只需删除或注释掉不需要的组件。

## 需要帮助？

- 原始模板文档: [README.md](./README.md)
- 模板仓库: https://github.com/JunyaoHu/academic-project-page-template-vue
- Element Plus组件文档: https://element-plus.org/zh-CN/

## 建议

1. **从简单开始**: 先只定制标题、作者和摘要
2. **频繁测试**: 每次修改后运行 `npm run dev` 查看效果
3. **参考示例**: 查看主 README.md 中的示例网站
4. **增量更新**: 可以先部署初始版本，之后再更新
5. **检查构建**: 提交前总是运行 `npm run build` 以尽早发现错误

祝您的KDD 2024论文宣传顺利！🎉

## 常见问题

### Q: 如何添加中文内容？
A: 直接在 `.mdx` 文件中使用中文即可，支持中英文混排。

### Q: 如何修改网站配色？
A: 在 `src/components/sections/Title.vue` 中修改 `title_color` 和 `btn_color` 等变量。

### Q: 如何添加更多作者？
A: 在 `Title.vue` 的 `authors` 数组中添加更多对象。

### Q: 可以去掉某些不需要的部分吗？
A: 可以，在 `src/components/Main.vue` 中注释或删除不需要的组件。
