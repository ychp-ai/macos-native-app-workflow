# motion · 原生动效

## 执行与交付

明确触发动作、交互反馈及当前 SwiftUI/AppKit 实现。只调整指定交互，处理快速反向操作、动画中断、任务取消和视图消失；避免动画阻塞点击或键盘操作。使用系统减少动态效果设置提供合适反馈，并检查缩放和高频更新时的流畅度。

按需读取 build-macos-apps:swiftui-patterns；涉及玻璃表面时读取 build-macos-apps:liquid-glass，窗口行为读取 build-macos-apps:window-management。具体 API 对照当前 SDK 和最低目标验证，不凭技能示例断言版本可用。

交付动效代码和触发/中断行为说明。使用真实界面观察验证，静态代码检查不能证明动画流畅度。
