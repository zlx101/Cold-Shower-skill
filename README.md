# 泼冷水 Skill

> 不要先问 AI「我这想法怎么样」。  
> 先问：「我这想法最可能在哪里崩？」

一个让 AI 先反驳、追问、拆解风险，再协助推进的 Codex skill。

它的目标不是让 AI 变刻薄，而是让 AI 在写代码、做方案、定产品、调定价、进入市场或做重大个人决定之前，先帮你把自信里最脆的部分打碎。

## 来源与署名

- Idea inspired by: 刘小排老师
- Skill maker: 成云杉

## 它比普通 Devil's Advocate 多什么

- **执行闸门**：每次冷水后给出 `Proceed / Clarify / Test / Kill` 判定。
- **六顶思考帽融合**：白帽看证据，红帽看情绪，黑帽找失败路径，黄帽保留成立的收益，绿帽给更小替代方案，蓝帽定下一步流程。
- **场景 playbook**：需求、架构、代码 review、产品、市场、pitch、个人重大决定分别有不同质疑角度。
- **证据纪律**：涉及市场、竞品、法律、价格、近期事实时，要求先查证，不靠编故事泼冷水。
- **退出条件**：泼不出来时明确停止，不把质疑变成表演。

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

### Codex

把仓库 clone 到 Codex skills 目录：

```powershell
git clone https://github.com/zlx101/pls-skill.git "$env:USERPROFILE\.codex\skills\cold-shower"
```

然后在 Codex 里使用：

```text
Use $cold-shower to pressure-test my product idea before implementation.
```

### 其他 Agent

把 [SKILL.md](./SKILL.md) 作为 system prompt 或技能说明加载即可。需要更完整模板时，再加载：

- [references/prompts.md](./references/prompts.md)
- [references/playbooks.md](./references/playbooks.md)

## 示例 Prompt

```text
我想做一个 AI 原生的一人公司工具，帮自由职业者自动接单、报价和交付。
请用 $cold-shower 泼冷水，并给出 Proceed / Clarify / Test / Kill 判定。
```

```text
这个架构方案看起来可行。
请用 $cold-shower 做一次极不友好的技术 review，重点找隐含假设、过度工程和未来技术债。
```

```text
我想从大厂离职 all in 做独立产品。
请用 $cold-shower 写一封 5 年后悔信，具体到我会失去什么。
```

## 文件结构

```text
.
├── SKILL.md
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
