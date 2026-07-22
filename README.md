# all-in-project-skill-lite

面向个人、小项目和单仓库多人协作的轻量项目全生命周期 Skill 套件。

它提供一个统一入口，根据当前任务路由到项目初始化、开发、需求评估与修改、Bug 修复、重构、代码审查、多人协作和分支合并等子 Skill。默认采用单人串行流程；涉及写入、合并、推送、删除或历史改写时，保留明确的用户确认门禁。

## 包含的 Skill

- 项目初始化与遗留项目接入
- 项目开发
- 需求评估与需求修改
- Bug 修复
- 重构协调与重构机会寻找
- 文档与项目同步检查
- 代码审查
- 多人协作与分支合并

## 安装

将仓库克隆到 Claude Code 的 Skills 目录：

```bash
git clone https://github.com/shuaimouls/all-in-project-skill-lite.git
```

具体安装位置取决于你的 Claude Code Skills 配置。

## 使用示例

在 Claude Code 中按自然语言描述任务，例如：

```text
从零初始化一个个人开发的 Todo 项目。
审查 feature/auth 相对 develop 的改动。
登录接口返回 500，按 Bug 修复流程处理。
检查项目文档与当前实现是否一致，先不要修改。
```

入口路由、安全门禁和各子 Skill 的完整说明见 [SKILL.md](SKILL.md)。
