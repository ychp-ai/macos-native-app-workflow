# windows · 窗口与菜单栏

## 执行与交付

明确目标是主窗口、辅助窗口、文档窗口、设置或菜单栏入口，以及启动、关闭、重开、多实例和状态恢复行为。使用 build-macos-apps:window-management；场景/菜单命令使用 build-macos-apps:swiftui-patterns；必要的 NSWindow、响应链或面板操作使用 build-macos-apps:appkit-interop。

先确认系统版本与支持的 scene API，保留现有应用激活策略。菜单栏应用必须有明确退出或恢复入口；隐藏标题栏时保持拖动、焦点与窗口操作可用。区分关闭窗口与退出应用，检查重复打开是否产生不期望实例以及每窗口状态归属。

实现后按需使用 build-macos-apps:build-run-debug，在真实前台 .app 中验证冷启动、关闭重开、切换焦点和适用的多窗口场景；没有 GUI 验证明确标注。交付指定窗口行为、实现和验证记录。
