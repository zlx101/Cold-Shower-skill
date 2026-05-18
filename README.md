# Cold Shower Skill / 泼冷水 Skill

> 不要先问 AI「我这想法怎么样」。  
> 先问：「我这想法最可能在哪里崩？」

一个通用 AI Agent skill / rule，让 AI 在写代码、做方案、定产品、调定价、进入市场或做重大个人决定之前，先反驳、追问、拆解风险，再协助推进。

## 为什么你需要「泼冷水 skill」

AI 默认对你友好。它私你、畏你、有求于你。所以它说“你的方案非常棒”，非常廉价。

AI 最危险的不是它会犯错，而是它会用同样的热情，帮你把一个烂想法做成产品级。

这个 Skill 反转 AI 的默认行为：让它在执行之前，先变成一个不急着讨好你的质疑者。

它会先追问需求、拆隐含假设、找失败路径、给出更小的验证方案，再决定这件事应该 Proceed、Clarify、Test，还是 Kill。

它不是单纯让 AI 唱反调，而是把「反驳」落到证据账本、最小验证、停止条件和下一步闸门上。

## 来源与署名

- idea来自：公众号：刘小排r
- 制作者：公众号：成云杉

## 适配范围

| 工具 | 适配方式 |
| --- | --- |
| Claude / Claude Code | 标准 Agent Skill：`SKILL.md` |
| Claude Code 项目级技能 | `.claude/skills/pls-skill/SKILL.md` |
| Codex | 标准 skill：`SKILL.md` + `agents/openai.yaml` |
| Cursor | `.cursor/rules/pls-skill.mdc` |
| Trae | `.trae/project_rules.md` 和 `.trae/rules/project_rules.md` |
| 其他 Agent | 直接加载 `SKILL.md`，需要模板时加载 `references/` |

## 适合场景

| 场景 | 你可以这样说 |
| --- | --- |
| 写代码前审视需求 | `先别写代码，用泼冷水模式追问我，直到需求清楚。` |
| 技术方案 review | `给我一次极不友好的架构冷水，找隐含假设和未来技术债。` |
| 产品/定价判断 | `扮演对我有偏见的投资人，说出最不想投我的 3 个理由。` |
| 市场进入 | `查一下这个赛道过去 5 年死掉的产品，我和它们哪里最像？` |
| Pitch / BP | `先不要帮我润色，先指出这个 pitch 哪里站不住。` |
| 个人重大决定 | `写一封 5 年后悔信，不许安慰，越具体越好。` |

## 安装

### Claude Code

用户级安装：

```powershell
git clone https://github.com/zlx101/Cold-Shower-skill.git "$env:USERPROFILE\.claude\skills\pls-skill"
```

项目级安装：

```powershell
New-Item -ItemType Directory -Force .\.claude\skills | Out-Null
git clone https://github.com/zlx101/Cold-Shower-skill.git .\.claude\skills\pls-skill
```

使用：

```text
Use pls-skill to pressure-test this plan before implementation.
```

### Claude

把仓库打包成包含 `SKILL.md` 的 skill 文件夹后上传。核心文件是：

```text
SKILL.md
references/prompts.md
references/playbooks.md
```

### Codex

```powershell
git clone https://github.com/zlx101/Cold-Shower-skill.git "$env:USERPROFILE\.codex\skills\pls-skill"
```

使用：

```text
Use $pls-skill to pressure-test my product idea before implementation.
```

### Cursor

复制 Cursor 规则到你的项目：

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules | Out-Null
Copy-Item .\Cold-Shower-skill\.cursor\rules\pls-skill.mdc .\.cursor\rules\pls-skill.mdc
```

使用：

```text
按 pls-skill 规则，先给这个方案泼冷水。
```

### Trae

复制或合并 Trae 项目规则。不同 Trae 版本/入口对规则路径支持略有差异，本仓库同时提供两个常见路径；优先使用你当前 Trae 自动生成或识别的那个。

```powershell
New-Item -ItemType Directory -Force .\.trae | Out-Null
Copy-Item .\Cold-Shower-skill\.trae\project_rules.md .\.trae\project_rules.md
```

如果你的 Trae 使用 `.trae/rules/project_rules.md`：

```powershell
New-Item -ItemType Directory -Force .\.trae\rules | Out-Null
Copy-Item .\Cold-Shower-skill\.trae\rules\project_rules.md .\.trae\rules\project_rules.md
```

如果项目里已经有规则文件，把本仓库里的内容追加进去，不要直接覆盖。

### 其他 Agent

把 [SKILL.md](./SKILL.md) 作为 system prompt、project instruction 或 rule 加载即可。需要更完整模板时，再加载：

- [references/prompts.md](./references/prompts.md)
- [references/playbooks.md](./references/playbooks.md)

## 示例 Prompt

```text
我想做一个 AI 原生的一人公司工具，帮自由职业者自动接单、报价和交付。
请用 pls-skill 泼冷水，并给出 Proceed / Clarify / Test / Kill 判定。
```

```text
这个架构方案看起来可行。
请用 pls-skill 做一次极不友好的技术 review，重点找隐含假设、过度工程和未来技术债。
```

```text
我想从大厂离职 all in 做独立产品。
请用 pls-skill 写一封 5 年后悔信，具体到我会失去什么。
```

## 文件结构

```text
.
├── SKILL.md
├── .claude/
│   └── skills/pls-skill/SKILL.md
├── .cursor/
│   └── rules/pls-skill.mdc
├── .trae/
│   ├── project_rules.md
│   └── rules/project_rules.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── playbooks.md
│   └── prompts.md
├── README.md
└── LICENSE
```

## License

MIT
