# all-in-project-skill-lite（1.4.0）

面向个人、小项目和单仓库多人协作的轻量项目全生命周期 Skill 套件。

它提供一个统一入口，根据当前任务路由到项目初始化、开发、需求评估与修改、Bug 修复、跨模块需求协调、重构、代码审查、多人协作、Goal 监工、最小上线评估、版本切分和前端页面/视觉规划等子 Skill。默认采用单人串行流程；跨模块需求协调通过需求包级第 0 层拆解、委派和验收，Goal 模式通过启动时逐项确认的精确授权合同连续推进，并以最短主上下文运行三层 Agent：第 0 层只调度和验收、最多同时委派 2 个第 1 层执行 Agent，每个第 1 层最多同时委派 1 个第 2 层局部 Agent，第 2 层不得继续委派。调用总次数不设预算，但合同外写入、合并、推送、删除或历史改写仍保留明确门禁。

## 包含的 Skill

- 项目初始化与遗留项目接入
- 项目开发
- 需求评估与需求修改
- Bug 修复
- 重构协调与重构机会寻找
- 文档与项目同步检查
- 代码审查
- 多人协作与分支合并
- 多需求协调
- Goal 监工
- 最小上线标准评估与版本功能分割
- 前端页面规划与视觉统一

## 快捷安装

使用第三方 `skills` CLI 安装到 Claude Code 的用户级 Skills 目录：

```bash
npx skills add shuaimouls/all-in-project-skill-lite --global --agent claude-code --yes
```

`skills` CLI 由 Vercel Labs 维护，并非 Anthropic 官方工具。Claude Code 目前没有用于安装任意 GitHub Skills 仓库的 `claude skills install` 命令。

## 手动安装

macOS、Linux 或 Git Bash：

```bash
mkdir -p "$HOME/.claude/skills" && \
git clone --depth 1 https://github.com/shuaimouls/all-in-project-skill-lite.git \
  "$HOME/.claude/skills/all-in-project-skill-lite"
```

Windows PowerShell：

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills" | Out-Null
git clone --depth 1 https://github.com/shuaimouls/all-in-project-skill-lite.git "$HOME\.claude\skills\all-in-project-skill-lite"
```

请保留仓库的完整目录结构；根入口依赖各中文子目录中的 `SKILL.md`。

## 使用示例

在 Claude Code 中按自然语言描述任务，例如：

```text
先把一个涉及认证、订单和通知的发布需求拆解、排依赖并协调多个 Agent。
文档和 vault 已完备，启动 Goal 监工推进 V0 到完成。
有 4 个可执行 vault，评估最快上线范围并拆分 V0/V1/V2。
先规划页面和导航，再生成 3 个离线视觉方向供选择。
审查 feature/auth 相对 develop 的改动。
登录接口返回 500，按 Bug 修复流程处理。
检查项目文档与当前实现是否一致，先不要修改。
```

入口路由、安全门禁和各子 Skill 的完整说明见 [SKILL.md](SKILL.md)。
