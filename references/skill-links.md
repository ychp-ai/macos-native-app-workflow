# 显式关联技能

从会话技能目录按完整名称定位 SKILL.md，不硬编码机器目录或插件版本。插件对外名称带 `build-macos-apps:` 前缀，源文件 frontmatter 可能仅使用短名称；插件内短名引用解析到同一插件。

| Skill | 职责 |
|---|---|
| `build-macos-apps:swiftui-patterns` | 场景、控件、菜单与桌面交互 |
| `build-macos-apps:appkit-interop` | SwiftUI/AppKit 桥接和响应链 |
| `build-macos-apps:window-management` | 窗口生命周期、外观和状态恢复 |
| `build-macos-apps:view-refactor` | 视图结构、状态归属和职责拆分 |
| `build-macos-apps:liquid-glass` | 适用系统版本上的玻璃材质设计 |
| `build-macos-apps:swiftpm-macos` | SwiftPM 产品、构建与测试 |
| `build-macos-apps:build-run-debug` | 工程发现、构建、GUI bundle 运行及调试 |
| `build-macos-apps:telemetry` | 为调试和测量增加必要日志 |
| `build-macos-apps:test-triage` | 测试失败分类和定向验证 |
| `build-macos-apps:signing-entitlements` | 签名、权限和 Gatekeeper 问题 |
| `build-macos-apps:packaging-notarization` | 分发产物、公证与打包验证 |
| `ui-ux-pro-max` | 视觉与交互规范，建议适配原生桌面 |
| `impeccable` | 界面评审与打磨，建议适配原生控件 |

## 按需使用

先根据入口的子命令映射选择，再读取实际使用项。相对引用基于被引用技能自身目录解析。安装状态及其必需依赖执行时检查，插件已安装不代表开发工具、证书或 GUI 自动化权限可用。

SwiftPM GUI 的构建可使用 swiftpm-macos，.app 包装与启动遵循 build-run-debug；命令行可执行文件和 GUI 应用的启动验证区分处理。已有工程保持自己的入口和构建配置。

通用设计技能用于视觉和交互原则，代码实现以 macOS 原生 API、当前 SDK 和目标系统版本为准。特定材质与窗口 API 的采用取决于兼容性和任务需要。
