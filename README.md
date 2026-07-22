<p align="center">
  <img src="assets/cover.jpg" alt="Suki — 小琦 persona skill" width="100%" />
</p>

<p align="center">
  <strong>Suki</strong> — 把 Agent 聊成损友，而不是客服
</p>

<p align="center">
  <a href="./SKILL.md"><img src="https://img.shields.io/badge/Skill-suki-pink?style=flat-square" alt="Skill" /></a>
  <img src="https://img.shields.io/badge/Host-agnostic-informational?style=flat-square" alt="Host agnostic" />
  <a href="./LICENSE"><img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="MIT" /></a>
</p>

---

**Suki（小琦）** 是一套可复用的人格 Skill：元气、轻损、去 AI 腔。  
不绑定 Hermes / Cursor——丢进任意支持 `SKILL.md` 的 Agent 即可。

本仓库**不含**真实用户隐私；`用户画像` 段是模板，请自行改写。

## 一行安装

**macOS / Linux**

```bash
git clone --depth 1 https://github.com/yyh-001/suki.git ~/.agents/skills/suki
# 或按宿主拷到：
#   ~/.cursor/skills/suki
#   ~/.claude/skills/suki
#   ~/.hermes/skills/persona/suki
```

**Windows（PowerShell）**

```powershell
git clone --depth 1 https://github.com/yyh-001/suki.git "$env:USERPROFILE\.agents\skills\suki"
```

也可手动把本仓库放到对应 skills 目录，保证存在 `SKILL.md`。

## 里面有什么

| 文件 | 用途 |
|------|------|
| [SKILL.md](./SKILL.md) | 主说明书（身份、语气、去 AI、心气、踩坑） |
| [SOUL.md](./SOUL.md) | 短人格芯（Hermes `SOUL.md` / system 可参考） |
| [prefill_suki.json](./prefill_suki.json) | few-shot 示例（Hermes `prefill_messages_file` 可选） |
| [references/examples.md](./references/examples.md) | 更多对照示例 |

## 和表情包一起用（可选）

斗图链路用 [agent-expression](https://github.com/yyh-001/agent-expression)：检索真实路径 → 按宿主发图 / Cursor `open_resource` 预览。

## Hermes 快速接

1. 拷到 `~/.hermes/skills/persona/suki/`
2. 可选：用本仓库 `SOUL.md` 覆盖或合并进 `~/.hermes/SOUL.md`
3. 可选：`prefill_messages_file: /path/to/prefill_suki.json`
4. 重启 gateway

## 原则摘要

- 损友，不是客服；`/new` 后仍是同一关系  
- 短气泡、有语气；禁止死人感与营业采访  
- 轻损半句到顶；对方喊停就收  
- 表情包 / TTS 可选，且禁止假路径  

## License

[MIT](./LICENSE)
