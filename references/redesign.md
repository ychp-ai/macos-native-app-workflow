# redesign · 页面与窗口重设计

## 执行与交付

从用户指定窗口/视图读取布局、事件、数据流、菜单、快捷键、设置和持久化状态。有预览能力时观察实际应用；没有截图不能声称已看到效果。盘点旧功能到新位置的映射，避免改版遗漏操作入口。

按需使用 build-macos-apps:swiftui-patterns、ui-ux-pro-max；窗口结构变化使用 build-macos-apps:window-management；需要拆分视图使用 build-macos-apps:view-refactor；视觉检查使用 impeccable。玻璃效果仅在适用时使用 build-macos-apps:liquid-glass。

“只出设计/重做页面设计”交付具体布局和交互规范；“重新设计并实现/重做窗口”完成代码与验证。保留业务合同、数据、快捷键和权限行为，除非用户明确要求调整。检查共享组件调用方，防止相邻窗口被连带改版。验证缩放、亮暗模式、键盘焦点、主要状态与原有操作。交付 redesign.md，实际实现时包含代码与验证结果。
