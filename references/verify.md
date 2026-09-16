# verify · 测试验收

## 执行与交付

读取范围与验收标准，识别 Xcode/SwiftPM 测试设施。按需使用 build-macos-apps:test-triage、build-macos-apps:build-run-debug、build-macos-apps:swiftpm-macos。执行最小有意义的测试集；失败时区分构建、断言、崩溃、环境和不稳定用例。

根据变更检查键盘/焦点、窗口生命周期、数据持久化、取消和失败恢复、权限拒绝、亮暗模式与窗口缩放。涉及目标系统或 CPU 架构的兼容性必须有对应环境证据，单机通过不能代表所有目标通过。只要求验收时不自动修复；要求修复则做相关回归。

交付 verification.md：环境、命令、测试结果、GUI 实际观察、复现步骤和未验证项。编译通过不等于界面验收，也不等于可分发。
