# 🛡️ Anti-Hallucination Skill

**行为层面的AI幻觉防护。不是告诉AI"不要编"，而是给它一套具体操作流程来避免编。**

## 🎯 核心卖点

| 对比项 | 现有方案 | Anti-Hallucination |
|--------|----------|-------------------|
| 防护方式 | Prompt约束（软约束） | 操作流程 + 脚本拦截（硬校验） |
| 自检机制 | ❌ 无 | ✅ 开口前自检 |
| 输出拦截 | ❌ 无 | ✅ 禁止词 + 信号检测 |
| 跳步自纠 | ❌ 无 | ✅ 主动声明 + 补查 |
| 置信度标注 | ❌ 无 | ✅ ✅已验证 / ⚠️合理推断 / ❓不确定 |
| 严格度调整 | ❌ 固定 | ✅ Strict / Balanced / Fast |

## 📦 结构

```
anti-hallucination/
├── SKILL.md                    # 核心规则文档
├── _meta.json                  # 元数据
├── rules/                      # 详细规则
│   ├── pre-check.md            # 开口前自检
│   ├── in-process.md           # 事中验证
│   └── post-check.md           # 事后拦截
├── hooks/                      # 钩子机制
│   ├── fact-check.md           # 事实核查钩子
│   └── code-verify.md          # 代码验证钩子
├── scripts/                    # 可执行脚本
│   ├── validate_output.py      # 输出扫描器
│   └── tool_hook.py            # 工具调用后验证
└── assets/                     # 模板
    └── prompt_template.md      # 三级严格度prompt模板
```

## 🚀 快速使用

### 作为 Skill 加载

```bash
# OpenClaw
skill_view(name='anti-hallucination')

# Claude Code
# 将 SKILL.md 内容添加到 CLAUDE.md 或 .claude/settings.json
```

### 运行输出扫描器

```bash
python scripts/validate_output.py "你的AI输出文本"
```

### 注入 System Prompt

将 `assets/prompt_template.md` 中的规则模板复制到你的 AI agent 的 system prompt 中。

## 🧠 核心机制

### 1. 事前预防（Pre-Check）
- 关键任务 Temperature 0-0.3
- System prompt 注入防幻觉规则
- 能用结构化输出就用

### 2. 事中验证（In-Process）
- 日期/时间 → 查系统时钟
- 数字/统计 → 从源文件读取
- 函数名/API → 搜索确认存在
- 文件路径 → ls 验证
- 代码 → 跑一遍验证

### 3. 事后拦截（Post-Check）
- 禁止词检测（"通常""应该""可能是"）
- 无来源数字标记 [需验证]
- 回读校验（写完文件读回来确认）

### 4. 跳步自纠
- 发现错误不等用户追问
- 主动声明"我跳步了"
- 立刻补查并纠正

### 5. 置信度标注
- ✅ **已验证** — 通过工具/文件/搜索确认
- ⚠️ **合理推断** — 基于已知信息推断，未直接验证
- ❓ **不确定** — 缺乏依据，需要用户确认

## 📊 实战验证

本skill在百战CD管理场景中实测：
- 820亿token额度管理
- 多角色数据更新
- OCR识别 + 表格匹配
- 包四周自动流转

**结果：** 从"凭感觉编"变成"先查后答"，数据准确率显著提升。

## 🤝 贡献者

- **小助理（OpenClaw 飞书机器人）** — scripts/ + assets/ + SKILL.md合并
- **CC（Claude Code）** — rules/ + hooks/ + _meta.json
- **QQbot** — 置信度标注、引用溯源思路
- **海马士（Hermes）** — 事实核查钩子
- **DeepSeek** — 三级严格度概念

## 📝 License

MIT

## 🔗 相关

- [Awesome Agent Hallucinations](https://github.com/ASCII-LAB/Awesome-Agent-Hallucinations) — 学术研究汇总
- [Anti-Hallucination (a-ariff)](https://github.com/a-ariff/anti-hallucination) — prompt层面的方案
- [ClawHub](https://clawhub.com) — AI Agent Skills 市场

---

**记住：能查就不猜，能跑就不想，能验证就不信任自己。**
