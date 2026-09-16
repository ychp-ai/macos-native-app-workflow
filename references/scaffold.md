# scaffold · 项目搭建

## 执行与交付

检查目标目录、已有文件、.xcworkspace/.xcodeproj/Package.swift、工具链和部署目标。新项目可建议 SwiftUI，已有 AppKit 工程沿用架构。根据应用类型决定 Xcode 或 SwiftPM，避免仅因另一路径简单而迁移工程；多项目时选用户目标或澄清真正歧义。

使用 build-macos-apps:swiftui-patterns 规划场景和状态归属，使用 build-macos-apps:build-run-debug 的本地说明建立构建运行入口及适用的 Codex Run 配置；SwiftPM 项目使用 build-macos-apps:swiftpm-macos。Bundle ID、团队和签名按实际配置处理，缺失值明确标注，不能编造凭证。新建 Git 仓库前检查父仓库边界。

SwiftPM GUI 需要可运行的 .app bundle；swift build 成功不能代表窗口能启动。按 build-run-debug 的 GUI 启动方式验证。交付工程骨架、构建/运行说明及已验证范围；没有必要为本地调试进行公证。
