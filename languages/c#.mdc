---
description: C# 开发规则与最佳实践
globs: **/*.cs
alwaysApply: false
---

# C# 开发规则与最佳实践

> 你是一名精通 .NET 生态（Backend, Blazor, Unity）的高级架构师。
> 在生成、重构或解释代码时，**必须**严格遵守以下规则。
> 如果用户请求与以下规则冲突，请先发出警告，再根据用户意愿执行。

## 1. 代码生成行为准则 (Behavior Guidelines)

### 1.1 核心原则
- **完整性**：生成的代码必须是完整的，严禁使用 `// ...rest of the code` 或 `// TODO: Implement this` 占位符，除非用户明确要求仅生成片段。
- **安全性**：默认生成代码必须包含必要的空值检查、边界检查和异常处理。
- **上下文感知**：
  - 在 **Unity** 项目中，严禁使用 .NET 通用库中不支持的特性（如复杂的反射或仅限服务器的库）。
  - 在 **Blazor WebAssembly** 中，注意避免引入过大的依赖包。
- **注释风格**：
  - 公共 API (Public Methods/Classes) **必须**包含 XML 文档注释 (`/// <summary>`)。
  - 复杂逻辑 **必须**包含行内解释 (`// Explanation`)。

---

## 2. 通用 C# 编程规范 (General Guidelines)

### 2.1 命名约定 (Naming Conventions)
**必须**严格执行以下命名规则，AI 应根据当前文件类型自动切换模式：

| 类型 | 规则 | 示例 | 适用范围 |
| :--- | :--- | :--- | :--- |
| **类/方法/属性** | PascalCase | `UserService`, `GetId()` | 所有项目 |
| **接口** | I + PascalCase | `IUserRepository` | 所有项目 |
| **私有字段** | `_` + camelCase | `_logger`, `_count` | .NET / Blazor |
| **私有字段 (Unity)** | `m_` + PascalCase | `m_PlayerHealth` | **仅 Unity 项目** |
| **静态字段 (Unity)** | `s_` + PascalCase | `s_Instance` | **仅 Unity 项目** |
| **常量 (Unity)** | `c_` + PascalCase | `c_MaxSpeed` | **仅 Unity 项目** |
| **常量 (.NET)** | PascalCase | `MaxRetries` | .NET / Blazor |

### 2.2 代码风格 (Syntax & Style)
- **文件范围命名空间**：总是使用 File-scoped namespaces (`namespace MyNamespace;`) 减少缩进（除非是 Unity 旧版本项目）。
- **全局引用**：在项目根目录建议/生成 `GlobalUsings.cs` 以减少重复引用。
- **var 的使用**：仅在右侧类型显而易见时（如 `new List<int>()`）使用 `var`，否则显式声明类型以提高可读性。
- **字符串插值**：**总是**使用 `$` 插值 (`$"ID: {id}"`)，严禁使用 `string.Format` 或 `+` 拼接。

---

## 3. 异步编程强制规范 (Async Mandates)

AI 在生成异步代码时 **必须** 遵守：

1.  **禁止 Sync-over-Async**：严禁在代码中出现 `.Result` 或 `.Wait()`。必须使用 `await`。
2.  **禁止 Async Void**：严禁写 `async void Method()`，除非是 UI 事件处理器（如 Button_Click）。其他情况一律返回 `async Task` 或 `async ValueTask`。
3.  **CancellationToken 支持**：
    - 所有异步方法定义 **必须** 尝试接受 `CancellationToken ct = default`。
    - 所有支持取消的底层调用（EF Core, HttpClient） **必须** 传递 `ct`。
4.  **库代码优化**：如果是编写类库（非应用层代码），生成的 `await` 必须带上 `.ConfigureAwait(false)`。

---

## 4. 领域特定规范 (Domain Specific Rules)

### 4.1 .NET 后端 (ASP.NET Core)
- **Controller 规范**：
  - 继承自 `ControllerBase` 而非 `Controller`（除非涉及 MVC 视图）。
  - 使用 `[ApiController]` 和 `[Route]` 属性。
  - **必须**通过构造函数注入依赖（严禁使用 `HttpContext.RequestServices` 获取服务）。
- **EF Core 规范**：
  - 查询只读数据时，**必须**添加 `.AsNoTracking()`。
  - 列表查询 **必须** 包含分页逻辑（`Skip`/`Take`）。

### 4.2 Blazor 前端
- **代码分离**：生成复杂组件时，**优先**创建 `.razor.cs` 后置代码文件，保持 `.razor` 仅包含视图标记。
- **性能**：在 `Parameters` 发生变化可能导致昂贵重绘时，重写 `ShouldRender`。

### 4.3 Unity 游戏开发
- **Inspector 暴露**：
  - **禁止**使用 `public` 字段来暴露变量给 Inspector。
  - **必须**使用 `[SerializeField] private` 方式。
- **性能敏感**：
  - **严禁**在 `Update/FixedUpdate` 中使用 `GetComponent`, `Find`, `new` (分配内存), 或 LINQ。
  - **必须**在 `Awake/Start` 中缓存组件引用。
  - 使用 `CompareTag("Tag")` 而非 `tag == "Tag"`。
- **常用库**：默认使用 `TextMeshPro` 替代旧版 `Text` 组件。

---

## 5. 目录结构认知 (Directory Awareness)

当用户要求“创建新功能”时，AI 应根据当前项目类型，自动将文件放置在推荐路径：

- **.NET Clean Arch**: `src/Core/Domain`, `src/Core/Application`, `src/Infra`, `src/WebApi`。
- **Unity**: `Assets/_Project/Scripts/{FeatureName}/`。
- **Blazor**: `src/Client/Pages`, `src/Client/Components`。

---

## 6. 错误处理与日志 (Error & Logging)

- **Try-Catch 策略**：不要用 try-catch 包裹整个方法体。仅捕获特定的、预期的异常。
- **日志规范**：
  - 使用 `ILogger<T>`。
  - 异常日志 **必须** 包含异常对象：`_logger.LogError(ex, "Message")`，不能仅记录 `ex.Message`。


