# Cursor Rules 规则汇总

本项目用于收集、整理和标准化 Cursor Rules 规则文件，提供多种编程语言和框架的规则支持，使开发者能够更有效地利用 Cursor 进行开发工作。

## Cursor Rules 最佳实践

文章教程：

[Cursor Rules 的一次全面总结，希望能够帮助到你！](https://mp.weixin.qq.com/s/l8r2lJlEv5fKWJRSsSd1kQ)

[Cursor 0.49.x 自动化生成 Project Rules 实用指南](https://mp.weixin.qq.com/s/1yTkzYzOFjty1D0gtYHuHA)

[Cursor Rules 进阶指南：打造企业级多语言开发规范](https://mp.weixin.qq.com/s/rfanrMtMMuyUTwsDYmlxSg)

[Cursor Rules 最佳实践总结](https://mp.weixin.qq.com/s/-J_LwfwH9rmFy4dzEy0RXg)

视频教程：

https://www.bilibili.com/video/BV1S3VhzpEqL/


### 1、通用规则层

这些规则始终生效，为所有代码提供基础规范：

- **core.mdc** - 核心开发原则和响应语言
- **tech-stack.mdc** - 技术栈定义和官方文档链接
- **project-structure.mdc** - 项目结构和文件组织规范
- **general.mdc** - 通用编程规则（后续将移除）

### 2、编程语言层

根据文件扩展名自动应用的语言特定规范：

- **Python** (python.mdc)
- **Java** (java.mdc)
- **TypeScript** (typescript.mdc)
- **Go** (golang.mdc)
- **C++** (c++.mdc)
- **CSS** (css.mdc)
- **WXML** (wxml.mdc) - 微信小程序标记语言
- **WXSS** (wxss.mdc) - 微信小程序样式表
- **Kotlin** (kotlin.mdc)
- **C#** (c#.mdc)

### 3、框架层

根据文件扩展名自动应用规范，或者AI可根据上下文自动判断并请求的框架特定规范：

#### 前端框架
- **React** (react.mdc) - React 应用开发
- **Vue.js** (vuejs.mdc) - Vue.js 应用开发
- **Next.js** (nextjs.mdc) - React 全栈框架
- **Tailwind CSS** (tailwind.mdc) - 实用优先的 CSS 框架

#### 后端框架
- **Django** (django.mdc) - Python Web 框架
- **Flask** (flask.mdc) - Python 轻量级 Web 框架
- **FastAPI** (fastapi.mdc) - Python 现代 API 框架
- **Spring Boot** (springboot.mdc) - Java 企业级框架

#### 移动开发框架
- **Flutter** (flutter.mdc) - 跨平台移动应用开发
- **SwiftUI** (swiftui.mdc) - iOS 原生 UI 框架
- **React Native** (react-native.mdc) - 跨平台移动应用开发
- **Android**(android.mdc) - Android 框架开发规范

###  4、其他工具层（可选，非必需）
需要用户明确请求的工具和流程规范，使用 `@` 引入对应的规则。

- **Git相关规则** (git.mdc)
- **Git Flow工作流规则** (gitflow.mdc)
- **文档编写规则** (document.mdc)


## 使用方法

1. 克隆本仓库
2. 浏览相应语言和框架的规则
3. 将适用的规则应用到您的项目中
4. 贡献您自己的规则回馈社区

## 项目结构

```
cursor-rules/
├── base/                    # 基础规则层（通用规则）
│   ├── core.mdc             # 核心开发原则和响应语言
│   ├── tech-stack.mdc       # 技术栈定义和官方文档链接
│   ├── project-structure.mdc # 项目结构和文件组织规范
│   └── general.mdc          # 通用编程规则
├── languages/               # 编程语言特定规则
│   ├── c++.mdc              # C++语言规则
│   ├── css.mdc              # CSS样式规则
│   ├── golang.mdc           # Go语言规则
│   ├── java.mdc             # Java语言规则
│   ├── kotlin.mdc           # Kotlin语言规则
│   ├── python.mdc           # Python语言规则
│   ├── typescript.mdc       # TypeScript语言规则
│   ├── wxml.mdc             # 微信小程序标记语言规则
│   └── wxss.mdc             # 微信小程序样式表规则
├── frameworks/              # 框架相关规则
│   ├── # 前端框架
│   ├── nextjs.mdc           # Next.js框架规则
│   ├── react.mdc            # React框架规则
│   ├── react-native.mdc     # React Native框架规则
│   ├── vuejs.mdc            # Vue.js框架规则
│   ├── tailwind.mdc         # Tailwind CSS规则
│   ├── # 后端框架
│   ├── django.mdc           # Django框架规则
│   ├── fastapi.mdc          # FastAPI框架规则
│   ├── flask.mdc            # Flask框架规则
│   ├── springboot.mdc       # Spring Boot框架规则
│   ├── # 移动开发框架
│   ├── android.mdc          # Android框架规则
│   ├── android_bak.mdc      # Android框架规则（备份版本）
│   ├── flutter.mdc          # Flutter框架规则
│   └── swiftui.mdc          # SwiftUI框架规则
├── other/                   # 其他工具层规则
│   ├── document.mdc         # 文档编写规则
│   ├── git.mdc              # Git相关规则
│   └── gitflow.mdc          # Git Flow工作流规则
└── demo/                    # 示例配置
    ├── python/              # Python项目示例配置
    └── vue/                 # Vue项目示例配置
```

## 贡献指南

欢迎提交Pull Request 或者提交 Issue 来分享您的Cursor规则。请确保您的规则文件遵循项目的命名约定和结构。规则可以使用Markdown(.mdc)或JSON格式。

## 许可证

MIT
