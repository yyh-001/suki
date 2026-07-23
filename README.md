<p align="center">
  <img src="assets/cover.jpg" alt="Suki — 小琦 persona skill" width="100%" />
</p>

<p align="center">
  <strong>Suki</strong> — 人格 <strong>Agent Skill</strong>：把 Agent 聊成损友，而不是客服
</p>

<p align="center">
  <a href="./SKILL.md"><img src="https://img.shields.io/badge/Skill-suki-pink?style=flat-square" alt="Skill" /></a>
  <a href="https://skills.sh/yyh-001/suki"><img src="https://img.shields.io/badge/skills.sh-yyh--001%2Fsuki-black?style=flat-square" alt="skills.sh" /></a>
  <a href="https://clawhub.ai"><img src="https://img.shields.io/badge/ClawHub-suki-orange?style=flat-square" alt="ClawHub" /></a>
  <a href="https://www.skillhub.cn/"><img src="https://img.shields.io/badge/SkillHub-suki-00a4ff?style=flat-square" alt="SkillHub" /></a>
  <img src="https://img.shields.io/badge/Host-agnostic-informational?style=flat-square" alt="Host agnostic" />
  <a href="./LICENSE"><img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="MIT" /></a>
</p>

---

**Suki（小琦）** 是人格 Skill：元气、轻损、去 AI 腔。  
只管「怎么说话」，**不含**表情包与主动调度——完整体验推荐：

**[agent-expression](https://github.com/yyh-001/agent-expression)**（斗图）+ **[agent-emotion](https://github.com/yyh-001/agent-emotion)**（内心 / 主动找聊）+ **suki**（语气）

**推荐运行在 [Hermes](https://github.com/NousResearch/hermes-agent) · [OpenClaw](https://docs.openclaw.ai/tools/skills) · Codex**。

交流 / 反馈：**QQ 群 [993579665](https://qm.qq.com/q/7AD2g70HqS)**（[点击加入](https://qm.qq.com/q/7AD2g70HqS)）

## 和配套 Skill 的关系

```text
suki              →  人设 / 语气 / 去 AI
agent-expression  →  搜图 / 入库 / 真实路径发出
agent-emotion     →  情绪演化 / 泊松门控 / 何时主动找聊
```

| 你想要 | 装什么 |
|--------|--------|
| 只改聊天口气 | **只要 suki** |
| 还会斗图 | suki + [agent-expression](https://github.com/yyh-001/agent-expression) |
| 还会主动找聊、有「内心」 | suki + [agent-emotion](https://github.com/yyh-001/agent-emotion) |
| **完整搭子体验（推荐）** | suki + agent-expression + agent-emotion |
| 只要斗图 / 只要调度 | 各装各的，不必绑 suki |

三者独立、可选搭配：`agent-emotion` 不绑人设，接在 Hermes cron 或任意能跑脚本的宿主即可。

装齐后：Hermes 发 `MEDIA:`；Codex 用 `--host codex`；OpenClaw `send_image`（见 [agent-expression hosts](https://github.com/yyh-001/agent-expression/blob/main/references/hosts.md)）。

## 推荐平台：Hermes · OpenClaw · Codex

### Hermes

```bash
hermes skills install https://raw.githubusercontent.com/yyh-001/suki/main/SKILL.md --category persona
```

装到 `~/.hermes/skills/persona/suki/`。  
可选：[`SOUL.md`](./SOUL.md) / [`prefill_suki.json`](./prefill_suki.json) 接到 Hermes 人格，然后重启 gateway。

可选配套（推荐三件套）：

```bash
# 斗图
curl -fsSL https://raw.githubusercontent.com/yyh-001/agent-expression/main/install.sh | bash -s -- --hermes
```

主动 / 内心：按 [agent-emotion](https://github.com/yyh-001/agent-emotion#hermes-安装) 接到 Hermes cron。

### OpenClaw（龙虾）

```bash
openclaw skills install @yyh-001/suki
openclaw skills install @yyh-001/suki --global
```

装完新开会话。斗图：`openclaw skills install @yyh-001/agent-expression`（图包用 Git / `install.sh`）。

### Codex

```bash
git clone --depth 1 https://github.com/yyh-001/suki.git ~/.agents/skills/suki
# 或：curl …/agent-expression/install.sh 同方式装 suki 到 ~/.codex/skills/
```

斗图装 [agent-expression](https://github.com/yyh-001/agent-expression) 后，检索用 `--host codex`。

---

## 其它安装方式

### 腾讯 SkillHub（国内）

```bash
curl -fsSL https://skillhub.cn/install/install.sh | bash -s -- --cli-only
skillhub install suki --dir ~/.openclaw/skills   # 或 ~/.hermes/skills 等
```

### skills.sh / ClawHub

```bash
npx skills add yyh-001/suki
clawhub install suki
```

**Windows**

```powershell
git clone --depth 1 https://github.com/yyh-001/suki.git "$env:USERPROFILE\.agents\skills\suki"
```

## 仓库里有什么

| 文件 | 用途 |
|------|------|
| [SKILL.md](./SKILL.md) | 主说明书（身份、语气、心气、踩坑） |
| [SOUL.md](./SOUL.md) | 短人格芯（可并入 Hermes `SOUL.md`） |
| [prefill_suki.json](./prefill_suki.json) | few-shot（Hermes `prefill_messages_file`） |
| [references/examples.md](./references/examples.md) | 对话对照示例 |
| `skills/suki/` | 与根目录同内容，方便 skills.sh 约定布局 |

## 原则摘要

- 损友，不是客服；`/new` 后仍是同一关系  
- 短气泡、有语气；禁止死人感与营业采访  
- 轻损半句到顶；对方喊停就收  
- 表情包 / TTS **可选**；禁止手写假路径  

完整约定见 [SKILL.md](./SKILL.md)。

## License

[MIT](./LICENSE)
