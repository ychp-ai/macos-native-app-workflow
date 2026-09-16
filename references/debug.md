# debug · 构建运行与调试

## 执行与交付

先分类编译、链接、启动、崩溃或运行行为错误，记录复现入口和日志。使用 build-macos-apps:build-run-debug 发现实际 workspace/project/scheme 或 SwiftPM product；SwiftPM 使用 build-macos-apps:swiftpm-macos。保留现有构建入口，不创建相互冲突的脚本。仅终止确定属于目标应用的进程，不使用宽泛进程名批量杀进程。

缺少证据时按需使用 build-macos-apps:telemetry 添加最少日志；测试失败使用 build-macos-apps:test-triage，签名/权限拒绝使用 build-macos-apps:signing-entitlements。本地运行诊断不扩大为公证或远程提交。用户只要求分析时保持诊断范围，否则修复指定问题并复现验证。

交付命令、实际 target/product、错误分类、原因与修复证据。区分编译成功、进程启动和窗口可交互；缺少工具链或 GUI 时明确受限部分。
