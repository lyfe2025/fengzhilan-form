# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

风之岚软件需求评估表单 — 一个面向潜在客户的软件定制开发需求收集页面。纯静态单文件项目，无构建工具、无外部依赖。

## 技术栈

- 单个 `index.html` 文件，内联 CSS + JavaScript
- 外部依赖仅 Google Fonts（Geist 字体），无 JS 依赖
- 表单提交通过 Formspree（`https://formspree.io/f/xdawgoew`）处理
- 面向移动端优先的响应式设计，黑白灰中性色调

## 开发方式

直接用浏览器打开 `index.html` 即可预览，无需任何构建或服务器。

## 设计风格

- 色系：纯黑白灰（neutral），参考名片岛项目
- 主色 `--primary: #171717`，背景 `--bg: #FAFAFA`，无彩色强调色
- 字体：Geist，回退到系统字体
- 圆角 10-14px，阴影层级 xs/sm/md/lg

## 页面结构（三屏切换）

1. **知识引导页** (`#guide-page`) — 手风琴折叠的软件科普、费用参考、合作须知
2. **表单页** (`#form-page`) — 7 道题：预算(必填) → 需求描述(必填) → 参考产品 → 平台选择 → 上线时间(必填) → 补充说明 → 联系方式(必填)
3. **成功页** (`#success-page`) — 提交成功后展示微信联系方式（支持点击复制）

三个页面通过 `.page-in` / `.page-out` 类切换（opacity + transform 动画），由 `flip()` 函数控制。

## 交互逻辑

- **手风琴**：互斥展开，CSS `grid-template-rows` 动画，chevron 旋转 90°
- **选项高亮**：选中后添加 `.on` 类（radio 同组互斥，checkbox 独立切换）
- **自动滚动**：radio 选中后 300ms 延迟自动滚到下一题（`data-next` 属性）
- **进度条**：sticky 顶部，实时统计 4 项必填完成数
- **提交按钮**：未完成显示「还差 X 项必填信息」并禁用，全部完成后启用 + shimmer 扫光
- **返回按钮**：表单页可返回引导页
- **预算警示**：选"2万以内"显示红色警示，选"暂时不确定"显示灰色提示
- **微信复制**：成功页微信卡片点击复制到剪贴板，带 toast 反馈
