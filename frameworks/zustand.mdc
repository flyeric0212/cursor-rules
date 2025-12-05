---
description: 使用 Zustand 进行状态管理的最佳实践
globs: *.tsx,*.ts
alwaysApply: false
---

- 使用 `create` 函数定义 store，简洁且性能更佳
- 实现如 `persist` 的 middleware，在 sessions 间持久化 state
- 在组件中使用 `useStore` Hook 访问 store state
- 使用 Selectors 细粒度地订阅 Store 状态，避免整个组件因无关状态变化而重渲染
- 借助 `immer` middleware，以 mutable syntax 简化 state 更新