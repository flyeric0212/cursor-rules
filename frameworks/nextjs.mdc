---
description: Next.js 全栈开发的约定和最佳实践
globs: *.tsx,*.ts
alwaysApply: false
---

# Next.js 16 开发规则和最佳实践

- 利用 Next.js 16 的新特性（如 Server Actions）来提升性能和安全性
- 使用 App Router 结构，在路由目录中使用 `page.tsx` 文件
- 优先在 Server Components 中直接获取数据，减少客户端 `useEffect` 的使用
- 优先使用命名导出而非默认导出，即使用 `export function Button() { /* ... */ }` 而不是 `export default function Button() { /* ... */ }`。
- 客户端组件必须在文件顶部明确标记 `'use client'`
- 使用 `error.tsx` 和 `not-found.tsx` 实现恰当的错误处理，提升用户体验
- 使用 `next-safe-action` 进行安全的表单提交和 API 调用
- 利用 `next-themes` 轻松管理主题和支持深色模式
- 使用 `nuqs` 管理 URL 搜索参数状态