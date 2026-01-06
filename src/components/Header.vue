<script lang="ts" setup>

import { ElIcon } from 'element-plus'
import { HomeFilled, Document, Link } from '@element-plus/icons-vue'

const baseUrl = import.meta.env.BASE_URL

const nav = {
    homepage: {
        name: "Homepage",
        link: "https://aster2024.github.io/",
        icon: HomeFilled,
    },
    home: {
        name: "SWIFT",
        link: baseUrl,
        icon: Link,
    },
    pdf: {
        name: "PDF",
        link: `${baseUrl}paper.pdf`,
        icon: Document,
    },
    arxiv: {
        name: "arXiv",
        link: "https://arxiv.org/abs/2505.12225",
        icon: Link,
    },
    slides: {
        name: "Slides",
        link: "https://docs.google.com/presentation/d/1MtUwGVC2xGDMu0b1TuJAujmfjxFn_TGt/edit?usp=sharing&ouid=101998927371723280988&rtpof=true&sd=true",
        icon: Link,
    },
}

</script>

<template>
    <!-- 设置页首始终悬浮顶部 -->
    <el-affix :offset="0" :style="{width: '100%'}">
    
    <!-- 水平导航目录 -->
    <el-menu 
        default-active="1"
        class="el-menu-demo"
        mode="horizontal"
        :ellipsis="false"
    >
        <el-menu-item index="0" >
            <el-icon :size="20"><component :is="nav.homepage.icon" /></el-icon>
            <a :href=nav.homepage.link target="_blank" rel="noopener">{{ nav.homepage.name }} </a>
        </el-menu-item>

        <el-menu-item index="1">
            <el-icon :size="20"><component :is="nav.home.icon" /></el-icon>
            <a :href=nav.home.link>{{ nav.home.name }} </a>
        </el-menu-item>

        <el-menu-item index="2">
            <el-icon :size="20"><component :is="nav.pdf.icon" /></el-icon>
            <a :href=nav.pdf.link target="_blank" rel="noopener">{{ nav.pdf.name }} </a>
        </el-menu-item>

        <el-menu-item index="3">
            <el-icon :size="20"><component :is="nav.arxiv.icon" /></el-icon>
            <a :href=nav.arxiv.link target="_blank" rel="noopener">{{ nav.arxiv.name }} </a>
        </el-menu-item>

        <el-menu-item index="4">
            <el-icon :size="20"><component :is="nav.slides.icon" /></el-icon>
            <a :href=nav.slides.link target="_blank" rel="noopener">{{ nav.slides.name }} </a>
        </el-menu-item>

    </el-menu>
    </el-affix>
</template>

<style>

/* 导航背景 */
.el-menu {
	background: none;
}

/* 下拉菜单宽度 */
.el-menu--popup {
	min-width: 100%;
}

/* 导航背景特效和阴影 */
.el-affix--fixed {
	box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
	background-image: radial-gradient(#ffffffca 1px,#ffffff 1px);
	background-size: 3px 3px;
}

/* 水平导航高度 */
.el-header {
    --el-header-height: 50px;
}

</style>

<style scoped>

/* 水平导航左右分区 */
.el-menu--horizontal > .el-menu-item:nth-child(1) {
    margin-right: auto;
}

/* 水平导航高度 */
.el-menu--horizontal {
    --el-menu-horizontal-height: 50px;
}

/* 取消鼠标焦点悬浮在链接上的颜色装饰 */
a:hover {
  color: inherit;
  border-bottom: none;
}

/* 链接装饰，取消下划线和链接颜色 */
a {
	text-decoration: None;
	color: inherit;
}

</style>

  