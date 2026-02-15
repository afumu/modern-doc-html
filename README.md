# 现代文档 HTML 生成器

将任何文档或内容转换为精美的现代化HTML页面，具有深色主题、渐变效果、卡片布局和流畅动画。

## 特性

- 🎨 **四种独立配色方案** - 经典蓝紫、赛博朋克、苹果极简、碳薄荷
- 🌙 **深色主题** - 专业的深色背景配合渐变光效
- 🎭 **多彩强调色系统** - 蓝、紫、绿、橙、青、粉六色可选
- 📦 **基于卡片的布局** - 带悬停动画的现代卡片设计
- ✨ **丰富的动画库** - 入场、连续和悬停动画
- 🎯 **Lucide图标支持** - 1000+现代SVG图标
- 💻 **代码块语法高亮** - 专业的代码展示
- 📱 **响应式设计** - 完美适配移动端和桌面端
- ♿ **无障碍支持** - 遵循 prefers-reduced-motion
- 🎬 **滚动触发动画** - 平滑的滚动淡入效果
- 📝 **内容自动居中** - 所有章节内容默认居中显示
- 📄 **分段写入支持** - 高效处理长文档

## 四种配色方案

### 1. 经典蓝紫（template-classic.html）- 默认推荐

**特点：** 专业科技感，蓝色+紫色渐变
**适用场景：** 技术文档、产品介绍、API文档
**色调：** 深蓝背景 + 蓝紫渐变强调色

### 2. 赛博朋克（template-cyberpunk.html）

**特点：** 霓虹发光效果，电光蓝+赛博粉+黑客绿
**适用场景：** 创意项目、游戏相关、未来科技主题
**色调：** 纯黑背景 + 霓虹色强调

### 3. 苹果极简（template-apple.html）

**特点：** 纯黑背景+纯白文字，极简高端
**适用场景：** 高端产品、设计作品、品牌展示
**色调：** #000000 背景 + #ffffff 文字

### 4. 碳薄荷（template-carbon.html）

**特点：** 炭黑+发光薄荷绿，硬核科技
**适用场景：** 开发工具、技术平台、性能展示
**色调：** 炭黑背景 + 薄荷绿强调色

## 快速开始

### 1. 选择配色方案

根据你的内容类型选择合适的模板：

- 技术文档 → `template-classic.html`
- 炫酷项目 → `template-cyberpunk.html`
- 高端产品 → `template-apple.html`
- 开发工具 → `template-carbon.html`

### 2. 替换占位符

模板中的占位符：

- `{{TITLE}}` - 页面标题（显示在浏览器标签）
- `{{BADGE}}` - 英雄区徽章文本（如 "PYTHON PROJECT"）
- `{{HERO_TITLE}}` - 主标题（可包含 `<span class="highlight">文本</span>` 实现渐变效果）
- `{{HERO_SUBTITLE}}` - 副标题文本
- `{{CONTENT}}` - 主要内容章节
- `{{FOOTER}}` - 页脚内容

### 3. 构建内容章节

每个章节遵循此模式：

```html
<section class="section center" id="section-id">
    <span class="section-label" style="background: rgba(168,85,247,0.15); color: var(--accent-purple);">标签</span>
    <h2>章节标题</h2>
    <p>章节描述...</p>

    <!-- 内容：卡片、代码块等 -->
</section>

<hr class="divider">
```

## 组件示例

### 带Lucide图标的卡片

```html
<div class="card-grid">
    <div class="card anim-scaleIn stagger-1">
        <div class="icon-wrapper circle">
            <i data-lucide="rocket" class="icon-lg icon-blue"></i>
        </div>
        <h3>卡片标题</h3>
        <p>卡片描述...</p>
    </div>
</div>
```

### 代码块

```html
<div class="code-block">
<span class="comment"># 注释</span>
<span class="keyword">def</span> <span class="func">function</span>():
    <span class="keyword">return</span> <span class="string">"value"</span>
</div>
```

### 带图标的章节标题

```html
<div class="section-header">
    <i data-lucide="zap" class="section-icon icon-purple anim-float"></i>
    <h2>章节标题</h2>
</div>
```

## 图标系统

### Lucide 图标

模板包含 Lucide Icons (https://lucide.dev) - 1000+现代SVG图标。

**图标尺寸：**
- `icon-sm` - 1rem (16px)
- `icon-md` - 1.5rem (24px)
- `icon-lg` - 2rem (32px)
- `icon-xl` - 3rem (48px)

**图标颜色：**
- `icon-blue` - 蓝色强调
- `icon-purple` - 紫色强调
- `icon-green` - 绿色强调
- `icon-orange` - 橙色强调
- `icon-cyan` - 青色强调
- `icon-pink` - 粉色强调

**图标包装器：**
- `icon-wrapper circle` - 圆形背景
- `icon-wrapper square` - 圆角方形背景

**常用图标名称：**
- `rocket`, `zap`, `star`, `heart`, `check-circle`, `alert-circle`
- `code`, `terminal`, `cpu`, `database`, `server`, `cloud`
- `user`, `users`, `mail`, `phone`, `calendar`, `clock`
- `arrow-right`, `chevron-down`, `menu`, `x`, `search`, `settings`

浏览所有图标：https://lucide.dev/icons

## 动画系统

### 入场动画

- `anim-slideInLeft` - 从左侧滑入
- `anim-slideInRight` - 从右侧滑入
- `anim-scaleIn` - 从小放大
- `anim-rotateIn` - 旋转淡入

### 连续动画

- `anim-float` - 轻柔的上下浮动（3秒循环）
- `anim-pulse` - 缩放脉冲效果（2秒循环）
- `anim-glow` - 发光边框效果（2秒循环）
- `anim-spin` - 持续旋转（2秒循环）
- `anim-shake` - 轻微抖动效果（0.5秒一次）

### 交错延迟

添加顺序延迟以创建交错动画：

- `stagger-1` - 0.1秒延迟
- `stagger-2` - 0.2秒延迟
- `stagger-3` - 0.3秒延迟
- `stagger-4` - 0.4秒延迟
- `stagger-5` - 0.5秒延迟
- `stagger-6` - 0.6秒延迟

**示例：**
```html
<div class="card anim-scaleIn stagger-1">卡片 1</div>
<div class="card anim-scaleIn stagger-2">卡片 2</div>
<div class="card anim-scaleIn stagger-3">卡片 3</div>
```

## 章节标签颜色

可用的颜色组合：

- 紫色：`background: rgba(168,85,247,0.15); color: var(--accent-purple);`
- 蓝色：`background: rgba(59,130,246,0.15); color: var(--accent-blue);`
- 绿色：`background: rgba(34,197,94,0.15); color: var(--accent-green);`
- 橙色：`background: rgba(249,115,22,0.15); color: var(--accent-orange);`
- 青色：`background: rgba(6,182,212,0.15); color: var(--accent-cyan);`
- 粉色：`background: rgba(236,72,153,0.15); color: #ec4899;`

## 处理长文档

对于超过3个主要章节的长文档，使用分段写入策略：

### 分段写入流程

1. **首次写入** - 创建HTML文件骨架
   - 使用 Write 工具创建完整的HTML文件
   - 包含：`<head>`、Hero区、前1-2个章节的内容、Footer、`</body></html>`
   - 确保HTML结构完整可用

2. **后续追加** - 逐步添加剩余章节
   - 使用 Edit 工具在 Footer 之前插入新章节
   - 每次追加2-3个章节
   - 保持HTML结构完整性

### 为什么要分段写入？

- 避免单次写入内容过长导致超时或截断
- 提高生成速度和成功率
- 便于调试和修改

## 使用技巧

- 使用表情符号作为卡片图标增加视觉趣味，或使用Lucide图标获得更现代的外观
- 在英雄标题的关键短语上应用渐变高亮：`<span class="highlight">文本</span>`
- 交替使用章节标签颜色以增加视觉多样性
- 保持段落简洁易读
- 在主要章节之间使用分隔线（`<hr class="divider">`）
- 对于中文内容，字体栈已包含 'Noto Sans SC'
- 代码块支持语法高亮，使用类：`.comment`、`.keyword`、`.string`、`.func`、`.symbol`
- 结合动画和交错延迟实现顺序显示效果
- 谨慎使用连续动画（float、pulse）以避免页面过于繁杂
- 图标通过 `lucide.createIcons()` 自动初始化 - 无需手动设置
- **重要：始终给section添加center类以确保内容居中显示**

## 文件结构

```
modern-doc-html/
├── SKILL.md                          # Skill 文档和工作流程
├── README.md                         # 本文件
└── references/
    ├── template-classic.html         # 经典蓝紫配色模板（默认）
    ├── template-cyberpunk.html       # 赛博朋克配色模板
    ├── template-apple.html           # 苹果极简配色模板
    └── template-carbon.html          # 碳薄荷配色模板
```

## 浏览器支持

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- 移动端浏览器（iOS Safari, Chrome Mobile）

## 相关资源

- [Lucide Icons](https://lucide.dev) - 图标库
- [MDN CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) - CSS动画文档
- [Intersection Observer API](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API) - 滚动动画实现

---

Built with ❤️ for modern documentation
