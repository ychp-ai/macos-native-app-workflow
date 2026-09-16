# release · 打包与发布

## 执行与交付

确定分发目标：本地归档、Developer ID 直接分发或 Mac App Store，以及本次动作：准备、构建/导出、签名、公证提交、装订验证或上传发布。选择与渠道匹配的流程，不能将直接分发公证流程套用于所有渠道。

使用 build-macos-apps:packaging-notarization、build-macos-apps:signing-entitlements，必要时 build-macos-apps:build-run-debug。检查实际版本、Bundle ID、产物架构、嵌套代码和签名、已有验收证据。依当前工具 help 和 Apple 官方文档核实具体命令，不编造证书、团队或服务端结果。

先完成可审阅产物和本地验证。用户对具体目标与外部提交已有授权时继续，不重复确认；“发布准备”只完成准备。“release”一词本身不代表授权所有提交和公开发布。工具或账号缺失时说明实际完成到哪一步；提交响应不明确先查状态，避免重复提交。密钥使用本机受支持的凭据管理方式。

交付 release.md：渠道、版本、产物路径、签名/公证/上传实际状态和剩余步骤。不要将完成打包描述为已公证或已发布。
