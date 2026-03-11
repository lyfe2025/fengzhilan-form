# 风之岚软件需求评估 设计系统

> 纯黑白灰中性配色，源自名片岛（mingpiandao）项目风格迁移
> 最后更新: 2026-03-11

## 设计方向

**风格**: 现代极简 · 克制精致
**调性**: 纯黑白灰高对比，无彩色强调，用留白和排版说话

## 配色方案

| 用途 | 颜色 | CSS 变量 |
|------|------|----------|
| 主色 | #171717 | --primary |
| 主色悬浮 | #262626 | --primary-hover |
| 强调色 | #171717 | --accent |
| 强调色浅底 | rgba(23,23,23,0.04) | --accent-soft |
| 强调色边框 | rgba(23,23,23,0.12) | --accent-border |
| 背景 | #FAFAFA | --bg |
| 卡片 | #FFFFFF | --surface |
| 正文 | #171717 | --text |
| 次要文字 | #404040 | --text-secondary |
| 辅助文字 | #A3A3A3 | --text-muted |
| 边框 | #E5E5E5 | --border |
| 浅边框 | #F5F5F5 | --border-light |
| 成功色 | #171717 | --success |
| 聚焦光圈 | rgba(23,23,23,0.12) | --ring |

## 字体

- **全局**: Geist（Google Fonts）
- **回退**: -apple-system, BlinkMacSystemFont, PingFang SC, Noto Sans SC

## 圆角

- 基础值: 10px (--radius)
- 输入框/按钮: 8px
- 卡片: 14px
- 标签: 4px
- 徽章: 100px (full)

## 阴影（递进）

- xs: `0 1px 2px rgba(0,0,0,0.04)`
- sm: `0 1px 3px rgba(0,0,0,0.04), 0 1px 2px rgba(0,0,0,0.06)`
- md: `0 4px 6px -1px rgba(0,0,0,0.06), 0 2px 4px -2px rgba(0,0,0,0.06)`
- lg: `0 10px 15px -3px rgba(0,0,0,0.08), 0 4px 6px -4px rgba(0,0,0,0.06)`

## 交互

- 过渡时长: 0.15s-0.2s ease
- 按钮 hover: translateY(-1px) + shadow 提升
- 按钮扫光: 6s shimmer 循环
- 输入框 focus: 3px ring (rgba(23,23,23,0.12))
- 选项选中: 背景 rgba(23,23,23,0.04) + 边框变深
- 手风琴展开/收起: 300ms ease-out, chevron 旋转 90°
- 页面切换: opacity + translateY 过渡, 200ms 延迟交错

## 禁止

- 不使用 Inter / Roboto / Arial
- 不使用彩色强调色（无暖金、无蓝色、无绿色作为品牌色）
- 不使用 emoji 作为图标
- 不使用重阴影（shadow-xl 以上）
- 不使用紫色渐变
