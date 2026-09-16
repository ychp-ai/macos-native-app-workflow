---
name: macos-native-app-workflow
description: "通过子命令完成 macOS 原生应用需求、SwiftUI/AppKit 设计开发、功能优化、窗口改版、调试、测试、签名和发布；支持独立执行指定节点。"
---

# macOS 原生应用工作流

## 调用方式

```text
$macos-native-app-workflow <子命令> <目标及要求>
```

这是 Codex 对话里的路由约定。按命令读取对应参考文件；路径始终相对于本 SKILL.md（包括软链接安装），业务项目由用户指定路径或当前工作项目确定。

| 子命令 | 能力 | 执行说明 |
|---|---|---|
| `requirements` | 需求梳理 | [requirements.md](references/requirements.md) |
| `design` | 原生 UI 设计 | [design.md](references/design.md) |
| `scaffold` | 项目搭建 | [scaffold.md](references/scaffold.md) |
| `feature` | 功能开发 | [feature.md](references/feature.md) |
| `optimize` | 现有功能优化 | [optimize.md](references/optimize.md) |
| `redesign` | 页面与窗口重设计 | [redesign.md](references/redesign.md) |
| `windows` | 窗口与菜单栏 | [windows.md](references/windows.md) |
| `motion` | 原生动效 | [motion.md](references/motion.md) |
| `polish` | 界面打磨 | [polish.md](references/polish.md) |
| `debug` | 构建运行与调试 | [debug.md](references/debug.md) |
| `verify` | 测试验收 | [verify.md](references/verify.md) |
| `signing` | 签名与权限 | [signing.md](references/signing.md) |
| `release` | 打包与发布 | [release.md](references/release.md) |

## 路由与范围

- `help`：展示命令和简短示例，不修改项目、不读取全部参考文件。
- 只加载选中节点。未给命令但目标明确时选择一个节点并简述；未知显式命令提示支持项，不猜测执行。没有默认 `all` 行为。
- 只有用户明确要求多个节点时才按指定顺序执行；必要的实现验证属于本节点，完成后停止，不自动发布。
- `feature` 实现指定功能；`optimize` 改进已有功能；`design` 制定新界面；`polish` 局部打磨；`redesign` 重做已有布局与视觉。
- “只分析/只设计”交付对应方案；“优化/修复/重新设计并实现”完成代码与相关验证。“重做页面设计”默认交付设计。目标描述里的命令词不算另一个节点。
- `debug` 处理构建运行问题，`verify` 验收指定行为；`signing` 处理签名权限，`release` 执行明确的分发步骤。子命令名本身不授予外部提交或公开发布权限。

## 共享执行约定

- 读取现有项目和用户材料即可开始，不要求先运行前置节点。只问真正阻塞当前工作的缺项；纯设计和需求不以证书、团队或构建环境为前置条件。
- 业务代码写入目标项目，不写入技能仓库。没有可识别项目时先确定代码目标目录；需求和设计可依据用户描述继续。
- 沿用已有 SwiftUI/AppKit、工程形态、存储和依赖方案。新应用优先评估 SwiftUI，AppKit 用于合适的原生场景或必要桥接，避免无关迁移。
- 实现前核实工具链、SDK 和最低 macOS 版本；新 API 需要可用性检查与适用回退。版本与 API 不确定时查本地 SDK 或 Apple 官方文档，不把参考示例当作兼容性证明。
- 按任务处理键盘、焦点、菜单、窗口生命周期、辅助功能、文件权限和状态恢复。只改变用户要求的行为，保护既有数据和未提交修改。
- 默认记录放项目已有文档位置，无约定时放 docs/macos/；多窗口报告用独立名称或小节。“不写文件/只读”直接在对话交付。“不修改代码”可按要求输出文档。
- 验证与风险匹配，区分静态检查、构建、测试、GUI 和分发证据。缺少工具或环境时如实列出未完成项，不伪造实际运行结果。
- 只说明实际使用的技能及阻塞当前工作的依赖问题。关联技能缺失时可完成自包含工作；读取的技能如要求必需依赖，先满足依赖再执行该操作，不绕过要求。

## 显式关联技能

从当前可用技能目录按精确名称定位；只读取实际需要的技能和其中有关的参考文件。使用关联技能不会自动启动本工作流的另一个子命令。详见 [关联清单](references/skill-links.md)。

| 子命令 | 关联 Skill 与适用条件 |
|---|---|
| `requirements` | 按本节点需求分析说明执行 |
| `design` | `build-macos-apps:swiftui-patterns`、`ui-ux-pro-max`；适用玻璃设计时 `build-macos-apps:liquid-glass` |
| `scaffold` | `build-macos-apps:swiftui-patterns`、`build-macos-apps:build-run-debug`；SwiftPM 工程使用 `build-macos-apps:swiftpm-macos` |
| `feature` | `build-macos-apps:swiftui-patterns`；桥接系统能力时 `build-macos-apps:appkit-interop` |
| `optimize` | `build-macos-apps:view-refactor`、`build-macos-apps:build-run-debug`；测量/日志时 `build-macos-apps:telemetry` |
| `redesign` | `build-macos-apps:swiftui-patterns`、`ui-ux-pro-max`、`impeccable`；按改动使用 `build-macos-apps:window-management`、`build-macos-apps:view-refactor`、`build-macos-apps:liquid-glass` |
| `windows` | `build-macos-apps:window-management`、`build-macos-apps:swiftui-patterns`、`build-macos-apps:appkit-interop`、`build-macos-apps:build-run-debug` |
| `motion` | `build-macos-apps:swiftui-patterns`；按需使用 `build-macos-apps:liquid-glass`、`build-macos-apps:window-management` |
| `polish` | `impeccable`、`ui-ux-pro-max`、`build-macos-apps:swiftui-patterns`；玻璃效果用 `build-macos-apps:liquid-glass` |
| `debug` | `build-macos-apps:build-run-debug`；按问题选 `build-macos-apps:swiftpm-macos`、`build-macos-apps:telemetry`、`build-macos-apps:test-triage`、`build-macos-apps:signing-entitlements` |
| `verify` | `build-macos-apps:test-triage`、`build-macos-apps:build-run-debug`；SwiftPM 测试用 `build-macos-apps:swiftpm-macos` |
| `signing` | `build-macos-apps:signing-entitlements` |
| `release` | `build-macos-apps:packaging-notarization`、`build-macos-apps:signing-entitlements`；构建时 `build-macos-apps:build-run-debug` |

## 示例

```text
$macos-native-app-workflow scaffold 创建带主窗口和设置窗口的 SwiftUI 应用。
$macos-native-app-workflow optimize 优化文件导入，保留数据格式，支持取消并验证。
$macos-native-app-workflow redesign 重新设计并实现设置窗口，保留原有设置项。
$macos-native-app-workflow windows 修复关闭主窗口后无法重新打开的问题。
$macos-native-app-workflow debug 排查应用启动后没有窗口的问题。
$macos-native-app-workflow release 只检查 Developer ID 分发准备情况，不提交公证。
```
