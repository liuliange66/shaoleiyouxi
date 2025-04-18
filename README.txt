# CSS 卡通风扫雷游戏 - v7 (完整功能 & 调试模式)

## 项目描述

这是一个使用纯 HTML, CSS, 和 JavaScript 实现的经典扫雷游戏项目。本项目旨在提供完整的扫雷体验，并配有高度定制化的、视觉上吸引人的可爱卡通风格用户界面。所有图形元素（图标、背景、开关等）均使用 CSS 技术模拟，无需外部图像资源。此版本包含了所有计划的核心功能、交互增强、动画效果，并内置了调试工具。

## 游戏截图

![游戏运行截图](在此处插入你的游戏截图.png)
*请将此占位符替换为实际的游戏截图*

## 主要特性

*   **核心扫雷玩法:**
    *   左键点击挖开 / 根据模式切换为插旗。
    *   右键点击始终可标记/取消标记地雷 🚩。
    *   数字提示（1-8），不同数字有不同颜色。
    *   空白区域 (0) 自动递归展开。
    *   首次点击安全保证。
    *   包含精确的胜利/失败条件判断。
*   **定制化卡通 UI (CSS 模拟):**
    *   **顶部状态栏:** 包含设置按钮 (⚙️)、帮助按钮 (❓)、实时计时器、关卡文字 ("第一关")、生命值（❤️ 视觉占位）、地雷计数器（带美化地雷图标 ⚫）。布局支持换行以适应不同宽度。
    *   **中央棋盘区域:** 圆角风格容器，动态计算单元格大小以适应屏幕。
    *   **单元格样式:** 独特的隐藏（米白）、揭示（棕色）状态。使用 CSS 模拟，无图片。
    *   **底部按钮区:**
        *   模式切换按钮 (⛏️/🚩)
        *   提示按钮 (💡)
        *   刷新按钮 (🔄)
        *   缩放按钮 (L 形 - 视觉占位)
*   **高级交互:**
    *   **单击数字高亮:** 点击已揭示数字，其邻居出现清晰的轮廓高亮（使用 `box-shadow` 实现，不遮挡内容）。
    *   **双击数字 Chording:** 当周围标记旗帜数等于数字时，双击可自动揭开安全邻居。包含对错误标记的检测，标错会导致游戏失败并显示 ❌。
    *   **模式切换:** 通过底部按钮切换左键的主要功能（挖开或插旗），按钮图标随之改变。
*   **动画效果:**
    *   揭开单元格的"掉落"动画（模拟方块长距离坠落）。
    *   揭示数字/空白格的"弹出"动画。
    *   地雷爆炸的"弹出"动画。
    *   放置旗帜时的"掉落"动画（旗帜从上方落下）。
    *   旗帜成功放置后的"摇晃"动画。
*   **动画与视觉：**
    *   爆炸地雷采用Q萌表情（大X眼、波浪嘴、大红舌头、爆炸星星），更具卡通趣味。
    *   插旗、揭开、爆炸等均有丰富动画和粒子特效。
*   **模态窗口:**
    *   **设置弹窗:** 点击设置按钮触发。包含：
        *   音效开关（可控制游戏音效）。
        *   音乐/震动开关（视觉占位）。
        *   放弃挑战按钮（功能已实现）。
        *   问题反馈/联系客服/用户 ID/协议链接（视觉占位）。
        *   使用 CSS 模拟 iOS 风格 Toggle 开关和手绘风格按钮边框。
    *   **帮助弹窗:** 点击帮助按钮触发，显示详细的游戏玩法说明。
*   **提示系统:**
    *   智能提示仅针对未被揭开的地雷，已爆炸雷不会被提示为目标。
    *   所有邻居格均可高亮，提示更直观。
    *   点击提示按钮 (💡) 可获得一次逻辑引导。
    *   系统会寻找棋盘上存在确定安全区或确定地雷区的数字格。
    *   **视觉提示:** 高亮相关区域（中心数字闪烁、邻居轮廓高亮）。若推断出地雷，会短暂**透视未打开的地雷格并闪烁地雷图标**。
    *   若无明显线索，会提示用户。
    *   默认每局可用一次（次数可在代码中配置）。
*   **游戏流程:**
    *   包含实时计时器。
    *   游戏结束后（胜利或失败）显示"再来一局"按钮，点击可重新开始。
*   **调试系统 (内置):**
    *   **页面内调试窗口:** 可通过按钮切换显示/隐藏，实时输出游戏日志和错误信息。方便用户反馈问题。
    *   **详细日志:** 代码中包含大量 `DEBUG:` 前缀的 `console.log` 和 `logDebug` 输出，追踪执行流程。
    *   **全局错误捕获:** `window.onerror` 捕获未处理的 JS 错误，并在控制台和调试窗口中显示。
*   **音效集成:** 集成了 `playSound` 函数和 `soundEnabled` 开关，只需提供音频文件路径即可启用音效。
*   **可访问性 (改进):** 为按钮、模态框、棋盘、单元格等添加了基础的 ARIA 属性。
*   **震动反馈：**
    *   支持多场景震动（爆炸强震、插旗轻震、胜利多段震等），可在设置中开关。
*   **代码注释与维护：**
    *   主要函数、核心逻辑、动画与交互等均有详细中文注释，便于二次开发和维护。

## 当前状态

*   **功能完整 (预期):** 包含上述所有核心功能、交互、动画和调试特性。
*   **可运行:** 根据用户最新反馈，此版本能够正常加载和运行。
*   **调试模式:** 代码中包含大量调试日志输出，调试窗口默认可能开启。在最终发布前可能需要移除或关闭这些调试特性。

## 技术栈

*   **HTML5:** 结构
*   **CSS3:** 样式, 布局 (Flexbox, Grid), 动画, 变量, 模拟图形
*   **JavaScript (ES6+):** 游戏逻辑, DOM 操作, 事件处理, 异步 (setTimeout/RAF), Audio API (接口), 错误处理

## 如何运行

1.  将代码保存为 `.html` 文件。
2.  在现代网页浏览器（如 Chrome, Firefox, Edge, Safari）中打开此文件。
3.  游戏应该会加载并可以开始游玩。
4.  （可选）通过页面上的按钮打开调试窗口查看详细日志。

## 自定义

*   **棋盘设置:** 在 `<script>` 标签内修改 `ROWS`, `COLS`, `MINES_COUNT`。
*   **提示次数:** 修改 `DEFAULT_HINTS_PER_GAME` 常量。
*   **音效:** 在 `sound` 对象中，将 `null` 替换为实际音频文件的路径。通过设置界面的开关控制音效是否播放。

## CSS 模拟说明

重申：界面中的所有视觉元素（图标、背景、开关等）均由 CSS 实现，非图片资源。效果是对手绘卡通风格的模仿。

---

这个 README 详细描述了 v7 版本（我们最后那个包含所有功能和调试代码的版本）应该具备的所有特性。如果它确实能正常运行，那么它就是一个功能相当完备的扫雷游戏了！