# 学术主页组件使用指南 Design by Si.X

这个项目包含了两个核心组件：双栏布局和卡片组件。以下是它们的详细使用说明。

## 双栏布局 (Double Column)

双栏布局允许你创建并排的两列内容，可以通过变量控制左右栏的宽度比例。在移动设备上会自动转换为上下布局。

### 基本用法

```html
<div class="double-column" style="--left-width: 0.4">
    <div class="left-column">
        <!-- 左栏内容 -->
    </div>
    <div class="right-column">
        <!-- 右栏内容 -->
    </div>
</div>
```

### 宽度控制

通过设置 `--left-width` CSS 变量来控制左栏宽度（取值 0-1）：
- `--left-width: 0.4` - 左栏占 40%，右栏占 60%
- `--left-width: 0.6` - 左栏占 60%，右栏占 40%
- `--left-width: 0.5` - 左右各占 50%

### 示例用法

```html
<!-- 图文布局（左图右文） -->
<div class="double-column" style="--left-width: 0.4">
    <div class="left-column">
        <img src="path/to/image.jpg" alt="Description">
    </div>
    <div class="right-column">
        <p>文字内容...</p>
    </div>
</div>

<!-- 内容分栏（等宽） -->
<div class="double-column" style="--left-width: 0.5">
    <div class="left-column">
        <h3>左侧标题</h3>
        <p>左侧内容...</p>
    </div>
    <div class="right-column">
        <h3>右侧标题</h3>
        <p>右侧内容...</p>
    </div>
</div>
```

## 卡片组件 (Card)

卡片组件提供了一个灵活的内容容器，支持标题、内容、背景图片或纯色背景。

### 基本结构

```html
<div class="card">
    <div class="card-content">
        <h3 class="card-title">标题</h3>
        <div class="card-body">
            <!-- 内容 -->
        </div>
    </div>
</div>
```

### 背景样式

1. 纯色背景：
```html
<div class="card" style="background-color: #f5f5f5;">
    <div class="card-content">
        <!-- 内容 -->
    </div>
</div>
```

2. 图片背景：
```html
<div class="card dark-theme">
    <div class="card-background" style="background-image: url('image.jpg')"></div>
    <div class="card-overlay"></div>
    <div class="card-content">
        <!-- 内容 -->
    </div>
</div>
```

### 特性
- 圆角边框（可通过 CSS 变量 `--card-radius` 调整）
- 内边距（可通过 CSS 变量 `--card-padding` 调整）
- 悬停效果（阴影加深和轻微上移）
- 暗色主题支持（添加 `dark-theme` 类）
- 自适应内容高度

### 完整示例

```html
<!-- 带图片背景的卡片 -->
<div class="card dark-theme">
    <div class="card-background" style="background-image: url('project-bg.jpg')"></div>
    <div class="card-overlay"></div>
    <div class="card-content">
        <h3 class="card-title">研究项目</h3>
        <div class="card-body">
            <p>项目描述...</p>
        </div>
    </div>
</div>

<!-- 纯色背景的卡片 -->
<div class="card" style="background-color: #f5f5f5;">
    <div class="card-content">
        <h3 class="card-title">项目概述</h3>
        <div class="card-body">
            <p>内容描述...</p>
            <ul>
                <li>要点一</li>
                <li>要点二</li>
            </ul>
        </div>
    </div>
</div>
```

## 响应式设计

- 双栏布局在移动设备（≤768px）上自动转换为上下布局
- 卡片组件自适应容器宽度
- 内容保持清晰可读