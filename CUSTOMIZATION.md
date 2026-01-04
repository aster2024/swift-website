# KDD Paper Promotional Website - Customization Guide

This website is customized for promoting your KDD 2024 accepted paper. Follow this guide to update it with your actual paper information.

## Quick Start

1. **Install dependencies**:
   ```bash
   npm install --force
   ```

2. **Run development server**:
   ```bash
   npm run dev
   ```

3. **Build for production**:
   ```bash
   npm run build
   ```

## Files to Customize

### 1. Title and Basic Information
**File**: `src/components/sections/Title.vue`

Update the following variables:

```javascript
// Paper title
const title = 'Your KDD Paper Title Here'  // Replace with your actual title

// Authors - add/remove entries as needed
const authors = [
  {
    name: "Author Name 1",           // Your actual name
    icon: "./icon/junyaohu.jpg",     // Your profile photo (add to public/icon/)
    homepage: "https://yourwebsite.com/",  // Your homepage URL
    address_flag: "1,*"              // Institution number and symbols
  },
  // Add more authors...
]

// Institutions
const addresses = [
  {
    address_flag: "1",
    name: "Your University",         // Your institution name
    icon: "./icon/home.png",         // Institution logo (add to public/icon/)
    homepage: "https://www.youruniversity.edu"  // Institution URL
  },
  // Add more institutions...
]

// Resource links - set disabled: false and add links when available
const buttons = [
  {
    disabled: false,  // Set to false when you have the link
    name: "Paper",
    link: "https://arxiv.org/abs/your-paper-id",  // Update with actual paper link
    component: Document,
  },
  {
    disabled: false,
    name: "Code",
    link: "https://github.com/yourusername/your-repo",  // Update with actual code repo
    component: Files,
  },
  // Update other buttons as needed
]
```

### 2. Abstract
**File**: `src/components/mds/abstract.mdx`

Replace the placeholder text with your actual paper abstract.

### 3. Main Content
**File**: `src/components/mds/md.mdx`

This file contains the main content of your promotional page. Update it with:
- Introduction to your research
- Key contributions
- Methodology overview
- Results and performance comparisons
- Conclusion

You can use Markdown syntax including:
- Headers (`#`, `##`, `###`)
- Lists (bulleted and numbered)
- Tables
- Links
- Images
- LaTeX equations (using `$$...$$`)
- Code blocks

### 4. BibTeX Citation
**File**: `src/components/sections/BibTeX.vue`

Update the BibTeX entry with your actual paper information:

```javascript
bibtex: [
  "@inproceedings{yourname2024yourtitle,",
  "    title={Your Actual Paper Title},",
  "    author={First Author and Second Author},",
  "    booktitle={Proceedings of the 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining},",
  "    year={2024},",
  "    organization={ACM}",
  "}",
]
```

### 5. Page Metadata
**File**: `index.html`

Update the page title and meta tags:

```html
<meta name="keywords" content="KDD, KDD 2024, Your Keywords">
<meta name="description" content="Brief description of your paper">
<title>Your Paper Title - KDD 2024</title>
```

### 6. Logo
**File**: `public/logo.png`

Replace with your project logo or leave as is. Referenced in `Title.vue` as:
```javascript
const logo = './logo.png'  // Set to '' to hide logo
```

### 7. Author Photos
**Directory**: `public/icon/`

Add your author profile photos to this directory and reference them in `Title.vue`.

## Adding Media Content

### Images
Place images in the `public/` directory and reference them in your `.mdx` files:
```markdown
![Alt text](./your-image.png)
```

### Videos
Edit `src/components/sections/Video.vue` to add videos (local, YouTube, or Bilibili).

### Carousel
Edit `src/components/sections/Carousel.vue` to add image carousels.

### Charts
Edit `src/components/sections/Echart.vue` to add interactive charts.

## GitHub Pages Deployment

This website is configured for GitHub Pages deployment at `https://aster2024.github.io/swift-website/`

The repository is already set up with GitHub Actions that will automatically build and deploy your site when you push changes.

### Deployment Steps:
1. Make your customizations locally
2. Test with `npm run dev`
3. Build with `npm run build` to verify no errors
4. Commit and push your changes
5. GitHub Actions will automatically deploy to the `gh-pages` branch
6. Your site will be live at `https://aster2024.github.io/swift-website/`

## Customizing Components

The website includes many optional components that you can show/hide in `src/components/Main.vue`:

```vue
<template>
  <Title/>           <!-- Always keep -->
  <Carousel/>        <!-- Remove if not needed -->
  <Video/>           <!-- Remove if not needed -->
  <Abstract/>        <!-- Always keep -->
  <Markdown/>        <!-- Always keep -->
  <Latex/>           <!-- Remove if not needed -->
  <Table/>           <!-- Remove if not needed -->
  <Collapse/>        <!-- Remove if not needed -->
  <Echart/>          <!-- Remove if not needed -->
  <!-- ... more components ... -->
  <BibTeX/>          <!-- Always keep -->
  <Comment/>         <!-- Remove if not needed -->
</template>
```

Simply remove or comment out components you don't need.

## Need Help?

- Original template documentation: [README.md](./README.md)
- Template repository: https://github.com/JunyaoHu/academic-project-page-template-vue
- Element Plus components: https://element-plus.org/

## Tips

1. **Start simple**: Begin by customizing just the title, authors, and abstract
2. **Test frequently**: Run `npm run dev` after each change to see the result
3. **Use examples**: Look at the example usage sites in the main README.md
4. **Incremental updates**: You can deploy an initial version and update it later
5. **Check build**: Always run `npm run build` before committing to catch errors early

Good luck with promoting your KDD 2024 paper! 🎉
