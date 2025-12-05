---
description: shadcn/ui 组件库使用规则和最佳实践
globs: **/*.tsx,**/*.ts,**/*.jsx
alwaysApply: false
---

# shadcn/ui 规则

- 优先使用 CLI (`pnpm dlx shadcn@latest add`) 添加新组件，以确保依赖和配置的完整性
- 所有的 shadcn 组件应统一存放在 `components/ui` 目录下，避免与其他业务组件混淆
- 使用 `cn` 工具函数（基于 `clsx` 和 `tailwind-merge`）来处理组件的 `className` 合并，确保样式可被正确覆盖
- 尽量避免直接修改 `components/ui` 下的原始组件代码，而是通过 Composition（组合）或 Props 扩展来定制功能
- 保持 Radix UI 原生的可访问性（Accessibility）特性，不要移除 `aria-*` 属性或破坏键盘导航逻辑
- 优先使用 `lucide-react` 作为图标库，以保持与 shadcn 设计风格的一致性
- 在构建复杂交互组件（如 DataTable, Form）时，严格遵循官方文档的 Composition 模式，不要过度抽象
