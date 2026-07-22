# all-in-project-skill-lite（1.5.0）

面向个人、小项目和单仓库多人协作的轻量项目全生命周期 Skill。

仓库只暴露一个入口 `SKILL.md`。入口根据完整 `$ARGUMENTS` 分派到 `references/` 中的内部流程规则，覆盖项目初始化、遗留项目接入、开发、需求评估与修改、Bug 修复、跨模块需求协调、重构、代码审查、多人协作、Goal 监工、最小上线评估、版本切分和前端页面/视觉规划。

默认采用单人串行流程；跨模块需求协调通过需求包级第 0 层拆解、委派和验收；Goal 模式通过启动时逐项确认的精确授权合同连续推进。合同外写入、合并、推送、删除或历史改写仍保留明确门禁。

## 内部流程

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

这些是根入口按需加载的内部规则，**不是独立可调用的 skills**。请只调用 `/all-in-project-skill-lite`，不要调用 `/项目开发`、`/Goal监工`，也不要调用 `Skill(项目开发)` 或 `Skill(Goal监工)`。

## 目录结构

```text
all-in-project-skill-lite/
├── SKILL.md                         # 唯一公开入口；根据 $ARGUMENTS 路由
├── README.md
└── references/                      # 仅供入口通过 Read 加载
    ├── shared-contract.md
    ├── goal-monitor.md
    ├── project-init.md
    ├── legacy-project-onboarding.md
    ├── project-development.md
    ├── requirement-assessment.md
    ├── requirement-change.md
    ├── refactor-coordination.md
    ├── bug-fix.md
    ├── docs-sync-check.md
    ├── refactor-opportunity.md
    ├── code-review.md
    ├── branch-merge.md
    ├── multi-agent-collaboration.md
    ├── multi-requirement-coordination.md
    ├── minimum-launch-assessment.md
    ├── version-splitting.md
    ├── frontend-page-planning.md
    └── frontend-visual-unification.md
```

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

请保留仓库的完整目录结构：根 `SKILL.md` 依赖 `references/` 内部规则，但只有根入口可被调用。

## 使用示例

在 Claude Code 中调用 `/all-in-project-skill-lite` 后按自然语言描述任务，例如：

```text
先把一个涉及认证、订单和通知的发布需求拆解、排依赖并协调多个 Agent。
文档和 vault 已完备，启动 Goal 监工推进 V0 到完成。
有 4 个可执行 vault，评估最快上线范围并拆分 V0/V1/V2。
先规划页面和导航，再生成 3 个离线视觉方向供选择。
审查 feature/auth 相对 develop 的改动。
登录接口返回 500，按 Bug 修复流程处理。
检查项目文档与当前实现是否一致，先不要修改。
```

入口路由、安全门禁与内部流程映射见 [SKILL.md](SKILL.md)。
