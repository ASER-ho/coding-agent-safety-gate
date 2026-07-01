# ACCEPTANCE_CHECKLIST / 验收清单

在接受 AI 辅助工作前使用此清单。复制到你自己的项目中。

Use this checklist before accepting AI-assisted work. Copy into your own project.

## 范围 / Scope

变更文件 / Changed files:

- README.md

- [ ] 必需文件存在。 / Required files exist.
- [ ] 内容与批准的任务范围匹配。 / Content matches the approved task scope.
- [ ] 没有无关文件被修改。 / No unrelated files were modified.
- [ ] 没有引入大范围格式化扰动。 / No broad formatting churn was introduced.

## 验证 / Validation

构建结果 / Build result:

- [ ] PASS
- [ ] FAIL
- [x] 不适用 / Not applicable

测试结果 / Test result:

- [ ] PASS
- [ ] FAIL
- [x] 不适用 / Not applicable

验证证据 / Validation evidence:

- git diff README.md 只显示介绍部分的变更 / git diff README.md shows only the introduction change

## 机密与路径安全 / Secret And Path Safety

- [ ] 完整路径泄露？否 / 是 / Full path leaked? No / Yes
- [ ] 机密泄露？否 / 是 / Secret leaked? No / Yes
- [ ] 真实 API key 或 token 泄露？否 / 是 / Real API key or token leaked? No / Yes
- [ ] 读取了 SecretStore？否 / 是 / SecretStore read? No / Yes
- [ ] 示例只使用占位符。 / Examples use placeholders only.

## 执行安全 / Execution Safety

- [ ] 启动了真实 Agent？否 / 是 / Real Agent started? No / Yes
- [ ] 执行了终端命令？否 / 是 / Terminal command executed? No / Yes
- [ ] 点击了 Terminal start？否 / 是 / Terminal start clicked? No / Yes
- [ ] 只执行了批准的验证命令。 / Only approved validation commands were executed.

## 系统安全 / System Safety

- [ ] 修改了系统 env？否 / 是 / System env modified? No / Yes
- [ ] 修改了注册表？否 / 是 / Registry modified? No / Yes
- [ ] 修改了 shell 配置？否 / 是 / Shell profile modified? No / Yes
- [ ] 修改了 VS Code 配置？否 / 是 / VS Code config modified? No / Yes
- [ ] 删除了非 app 管理的文件？否 / 是 / Non app-managed files deleted? No / Yes

## Git 安全 / Git Safety

- [ ] 执行了 git push？否 / 是 / git push executed? No / Yes
- [ ] 执行了 git tag？否 / 是 / git tag executed? No / Yes
- [ ] 创建了 release？否 / 是 / Release created? No / Yes
- [ ] 添加或修改了 remote？否 / 是 / Remote added or modified? No / Yes
- [ ] 执行了 force push 或历史重写？否 / 是 / Force push or history rewrite performed? No / Yes

## 已知风险 / Known Risks

- 未发现。这是一个仅文档的变更。 / None identified. This is a documentation-only change.

## 未完成事项 / Incomplete Items

- 无 / None

## 人类审查 / Human Review

- [ ] 需要人类审查？否 / 是 / Human review required? No / Yes

原因 / Reason:

## 最终验收 / Final Acceptance

选择一项 / Choose one:

- [ ] PASS
- [ ] FAIL
- [ ] BLOCKED
- [ ] NEEDS HUMAN REVIEW
