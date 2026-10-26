## 变更说明

[English](PULL_REQUEST_TEMPLATE.en.md) | **简体中文**

<!-- 说明问题、方案和用户可见影响。 -->

## 验证

<!-- 列出实际执行的命令、测试环境和结果。 -->

- [ ] Rust fmt、Clippy 和 workspace tests（如适用）
- [ ] macOS Debug build（如适用）
- [ ] 新增或更新测试（如适用）
- [ ] 文档与当前实现一致

## 安全与隐私

- [ ] 未新增网络 payload、凭据、Cookie、文件正文或其他敏感内容采集
- [ ] 新权限、entitlement、外部请求和数据保留变化已明确说明并更新文档
- [ ] 缺失 capability 会显示为 unavailable/skipped，不会被解释为“没有风险”
- [ ] 日志、截图和测试数据均已脱敏

## 兼容性

- [ ] Protobuf 变更保持 field number 与语义兼容（如适用）
- [ ] 数据库迁移、平台降级和回滚路径已考虑（如适用）

关联 Issue：
