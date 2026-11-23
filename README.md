# 创意与设计 Agent

面向 Codex 的中文创意与设计工作流。简单任务直接比较可用成品，复杂项目先用提案和代表性样稿确定方向，再组织制作与验收。

[下载 Agent 和配套 Skill 1.0.0](creative-design-agent-v1.0.0.zip?raw=true)

## 安装与使用

1. 下载并解压压缩包，打开其中的 `creative-design-agent` 文件夹。
2. 将 `skills/creative-design` 目录复制到 `~/.agents/skills/`，将 `agents/creative-design.toml` 复制到 `~/.codex/agents/`。自定义 `CODEX_HOME` 的用户将角色文件放入该目录的 `agents/`。已有同名文件时先核对版本。
3. 新开 Codex 会话，用 `$creative-design` 调用工作流程，或要求“调用 creative-design 子智能体”。

包内含角色配置、完整 Skill 源码、三份工作参考和只读能力盘点脚本。盘点脚本的依赖 PyYAML 6.0.3 随包提供，原作者署名与 MIT 许可保存在包内。第三方设计和文案 Skills 可按任务另行安装。
