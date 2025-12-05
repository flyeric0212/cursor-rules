---
description: React 19 组件模式、Hooks 与最佳实践
globs: **/*.jsx,**/*.tsx
alwaysApply: false
---

# React 19 规则

- 优先使用函数式组件（Functional Components）与 Hooks
- 拥抱 React 19 的 Actions 机制，使用 `useActionState` 和 `useFormStatus` 管理表单提交与加载状态
- 直接将 `ref` 作为 prop 传递给组件，不再使用 `forwardRef` 包装组件
- 使用 `use` API 读取 Context (`const theme = use(ThemeContext)`) 和 Promise，替代 `useContext`
- 使用 `<Context>` 直接作为 Provider (如 `<ThemeContext value="dark">`)，不再需要 `<Context.Provider>`
- 仅在必要时（如传递给昂贵计算的子组件）手动使用 `useCallback` 与 `useMemo`，若项目已启用 React Compiler 则由编译器自动优化
- 使用 TypeScript 进行严格的 Props 类型定义
- 对于复杂表单校验，结合 `react-hook-form` 与 Zod 使用；简单表单优先使用原生 Action
- 使用 Zustand 处理跨组件的复杂客户端状态，避免 Context 嵌套地狱
