# NOTICE

本仓库是 **Miniclaw** 源码快照的深入学习与二次开发版本。

- 上游项目：<https://github.com/helsome/miniclaw>
- 源码快照获取时间：2026-08
- 上游仓库状态：截至 2026-11-18 已不可公开访问（GitHub 返回 404）

原始代码版权归 Miniclaw contributors 所有，按 MIT License 分发，完整授权文本见
[LICENSE](LICENSE)。

## 本地修改

本仓库在源码快照基础上做了以下修改：

1. `src/effective-skill-resolver.ts`：Windows 普通用户没有
   `SeCreateSymbolicLinkPrivilege`，`fs.symlinkSync` 会直接抛出 `EPERM`。
   Skill 均为目录，改为在 Windows 上使用 `junction` 创建链接，其他平台保持
   原有 symlink 语义。该修改单独提交，可在 git log 中查看。
2. `container/agent-runner/src/` 下的少量运行期调试调整，包含在初始快照提交中。

本说明仅用于标注来源，不修改、不替代原始版权声明。
