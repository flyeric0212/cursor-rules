---
description: Tailwind CSS 编码规则和最佳实践
globs: **/*.tsx,**/*.ts,**/*.jsx,**/*.css
alwaysApply: false
---

# Tailwind CSS 规则

- 采用移动优先（Mobile-First）的响应式设计策略，默认编写移动端样式，使用 `sm:`, `md:`, `lg:` 等前缀覆盖大屏样式
- 使用 `clsx` 或 `tailwind-merge` 动态合并类名，确保组件样式的可覆盖性与无冲突
- 优先直接在 JSX 中使用 Utility Classes，仅在极高复用场景下谨慎使用 `@apply` 提取样式，避免过早抽象
- 使用 `group` 和 `peer` 修饰符处理父子组件或兄弟组件间的状态交互（如 hover, focus）
- 避免在代码中使用任意值（Arbitrary values，如 `w-[123px]`），优先遵循设计系统的 Token 规范
- 保持 class 顺序的一致性，建议配置 `prettier-plugin-tailwindcss` 自动排序
- 使用 `space-x/y` 或 `gap` 工具类管理布局间距，而非手动添加 margin