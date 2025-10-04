# 三原色对决 (Primary Color Duel)

一个双人对战的网页小游戏：通过调节 R/G/B 滑杆或键盘快捷键，让自己的颜色尽可能接近系统随机生成的目标颜色，匹配度更高者获胜。

- 玩法亮点：
  - 双人同时操作（键盘长按、Shift 加速）
  - 实时匹配度与进度条反馈
  - 任一方 ≥ 95% 即判定胜利并锁定

## 本地运行

直接用浏览器打开 `index.html` 即可游玩。

## 键位说明

- Player A：
  - R: Q 增加 / A 减少
  - G: W 增加 / S 减少
  - B: E 增加 / D 减少
- Player B：
  - R: U 增加 / J 减少
  - G: I 增加 / K 减少
  - B: O 增加 / L 减少
- 加速：按住 Shift（步进从 1 → 5）

## 目录结构

- `index.html`: 完整页面（布局、样式、交互脚本）
- `README.md`: 本说明文档

## 开发说明（简要）

- 使用原生 HTML/CSS/JavaScript 实现，无需构建或依赖。
- 相似度算法：
  ```js
  function colorSimilarity(c1, c2) {
    const distance = Math.sqrt(
      Math.pow(c1.r - c2.r, 2) +
      Math.pow(c1.g - c2.g, 2) +
      Math.pow(c1.b - c2.b, 2)
    );
    return Math.max(0, 100 - (distance / 4.42));
  }
  ```

## 部署

- 可直接将本仓库设为 GitHub Pages，或部署到任意静态托管平台。
