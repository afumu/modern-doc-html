---
name: modern-doc-html
description: 将文档和内容转换为现代化、深色主题的HTML页面，包含渐变效果、卡片布局和流畅动画。适用于：(1) 将文档/文章转换为现代设计的HTML，(2) 创建技术文档页面，(3) 生成演示风格的网页，(4) 提到"现代HTML"、"深色主题HTML"、"技术文档HTML"，或 (5) 想要类似learn-claude-code风格的HTML输出。
---

# 现代文档 HTML 生成器

将任何文档或内容转换为精美的现代化HTML页面，具有深色主题、渐变效果、卡片布局和流畅动画。

## 工作流程

1. **理解内容结构**
   - 阅读源文档/内容
   - 识别主要章节和层次结构
   - 注意任何特殊元素（代码块、列表、表格）

2. **提取关键信息**
   - 标题和副标题
   - 徽章文本（可选的分类/标签）
   - 主要章节及标题
   - 内容段落
   - 特殊元素（卡片、代码块等）

3. **使用模板生成HTML**
   - 从 `references/template.html` 读取模板
   - 替换占位符：
     - `{{TITLE}}` - 页面标题
     - `{{BADGE}}` - 英雄区徽章文本
     - `{{HERO_TITLE}}` - 主标题（可包含 `<span class="highlight">文本</span>` 实现渐变效果）
     - `{{HERO_SUBTITLE}}` - 副标题文本
     - `{{CONTENT}}` - 主要内容章节
     - `{{FOOTER}}` - 页脚内容

4. **构建内容章节**
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

   **重要：** 默认给所有 `<section>` 添加 `center` 类以确保内容居中：
   ```html
   <section class="section center" id="section-id">
   ```

5. **使用适当的内容组件**

   **带表情符号图标的卡片网格：**
   ```html
   <div class="card-grid">
       <div class="card">
           <div class="card-icon">🎯</div>
           <h3>卡片标题</h3>
           <p>卡片描述...</p>
       </div>
   </div>
   ```

   **带Lucide图标的卡片网格：**
   ```html
   <div class="card-grid">
       <div class="card">
           <div class="icon-wrapper circle">
               <i data-lucide="rocket" class="icon-lg icon-blue"></i>
           </div>
           <h3>卡片标题</h3>
           <p>卡片描述...</p>
       </div>
   </div>
   ```

   **带图标的章节标题：**
   ```html
   <div class="section-header">
       <i data-lucide="zap" class="section-icon icon-purple anim-float"></i>
       <h2>章节标题</h2>
   </div>
   ```

   **图标盒子：**
   ```html
   <div class="icon-box anim-pulse">
       <i data-lucide="check-circle" class="icon-xl icon-green"></i>
   </div>
   ```

   **代码块：**
   ```html
   <div class="code-block">
   <span class="comment"># 注释</span>
   <span class="keyword">def</span> <span class="func">function</span>():
       <span class="keyword">return</span> <span class="string">"value"</span>
   </div>
   ```

6. **选择章节标签颜色**
   可用的颜色组合：
   - 紫色：`background: rgba(168,85,247,0.15); color: var(--accent-purple);`
   - 蓝色：`background: rgba(59,130,246,0.15); color: var(--accent-blue);`
   - 绿色：`background: rgba(34,197,94,0.15); color: var(--accent-green);`
   - 橙色：`background: rgba(249,115,22,0.15); color: var(--accent-orange);`
   - 青色：`background: rgba(6,182,212,0.15); color: var(--accent-cyan);`
   - 粉色：`background: rgba(236,72,153,0.15); color: #ec4899;`

7. **编写最终HTML文件**
   - 保存到用户指定位置或建议文件名
   - 确保正确的HTML结构和闭合标签
   - **确保所有section都添加了center类以保持居中**

## 设计特性

- **深色主题** 配合渐变光效
- **四种科技感配色方案** 可实时切换：
  - **经典蓝紫**（默认）：专业科技感，蓝色+紫色渐变
  - **赛博朋克**：霓虹发光效果，电光蓝+赛博粉+黑客绿，未来感强烈
  - **苹果极简**：纯黑背景+纯白文字，极简高端，专业优雅
  - **碳薄荷**：炭黑+发光薄荷绿，硬核科技，高性能感
- **多彩强调色系统**（蓝、紫、绿、橙、青、粉）
- **基于卡片的布局** 带悬停动画
- **滚动时平滑淡入动画**
- **代码块语法高亮**
- **响应式设计** 适配移动端和桌面端
- **英雄区** 带动画徽章和箭头
- **Lucide图标** - 通过CDN提供1000+现代SVG图标
- **丰富的动画库** - 入场、连续和悬停动画
- **图标支持** - 支持表情符号和SVG图标，带样式选项
- **内容自动居中** - 所有章节内容默认居中显示
- **主题记忆功能** - 用户选择的配色会自动保存

## 图标使用指南

### Lucide 图标

模板包含 Lucide Icons (https://lucide.dev) - 一个现代、轻量级的图标库，拥有1000+图标。

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
- 浏览所有图标请访问 https://lucide.dev/icons

### 表情符号图标

传统表情符号图标仍然适用于快速、多彩的图标：
```html
<div class="card-icon">🎯</div>
```

## 动画指南

### 入场动画

应用于首次出现时需要动画的元素：

- `anim-slideInLeft` - 从左侧滑入
- `anim-slideInRight` - 从右侧滑入
- `anim-scaleIn` - 从小放大
- `anim-rotateIn` - 旋转淡入

**示例：**
```html
<div class="card anim-slideInLeft">...</div>
```

### 连续动画

应用于需要持续动画的元素：

- `anim-float` - 轻柔的上下浮动（3秒循环）
- `anim-pulse` - 缩放脉冲效果（2秒循环）
- `anim-glow` - 发光边框效果（2秒循环）
- `anim-spin` - 持续旋转（2秒循环）
- `anim-shake` - 轻微抖动效果（0.5秒一次）

**示例：**
```html
<i data-lucide="zap" class="icon-lg icon-purple anim-float"></i>
```

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

### 无障碍支持

所有动画都遵循 `prefers-reduced-motion` - 偏好减少动画的用户将看到即时过渡而非动画。

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
- 浏览所有可用的Lucide图标请访问 https://lucide.dev/icons
- **重要：始终给section添加center类以确保内容居中显示**

## 示例用法

用户："将这个markdown文档转换为现代HTML"
→ 读取文档，提取结构，使用模板生成HTML

用户："为这个API文档创建技术文档页面"
→ 将API文档结构化为带代码示例的章节，生成HTML

用户："制作一个类似learn-claude-code风格的HTML页面"
→ 使用模板创建类似的深色主题、现代布局
