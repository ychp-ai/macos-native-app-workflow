# signing · 签名与权限

## 执行与交付

读取用户目标是本地开发、签名诊断还是分发配置。使用 build-macos-apps:signing-entitlements，先检查真实产物/项目、Bundle ID、签名身份、entitlements、sandbox、hardened runtime 和嵌套代码；发现问题后做最小必要修复。

使用实际可用的身份与配置，不生成虚假的团队或证书，不把私钥/密码写入仓库。权限必须对应实际功能，不以关闭 sandbox、Gatekeeper 或移除隔离属性掩盖根因。诊断请求先保留产物证据，明确要求修复时再修改相关配置或重签目标产物。

交付 signing.md：检查对象、真实状态、问题类别、变更和验证。区分本地调试签名与分发签名，不把公证作为日常本地运行前置条件。不自动提交到 Apple。
