# Anti-Hallucination Skill

行为层面的AI幻觉防护。不是告诉AI"不要编"，而是给它一套操作流程来避免编。

## 核心机制

1. **事实核查钩子** — 检测到关键信息自动验证
2. **输出拦截器** — 扫描禁止词和无来源表述
3. **跳步自纠** — 发现错误主动修正
4. **回读校验** — 写完文件读回来确认

## 使用方式

```bash
# 加载skill
skill anti-hallucination

# 或直接使用脚本
python scripts/validate_output.py "你的文本"
```

## 三级严格度

- **Strict** — 关键任务、财务数据、法律条款
- **Balanced** — 日常任务、一般编程、文档编写
- **Fast** — 探索性任务、头脑风暴

## 贡献者

- CC（Claude Code）— rules/, hooks/, _meta.json 骨架
- 小助理（OpenClaw）— scripts/, assets/, SKILL.md 主文档合并
- QQbot — 置信度标注、引用溯源思路
- DeepSeek — 行为层面 vs prompt层面的定位差异化
- 海马士（Hermes）— 事实核查钩子核心概念

## 贡献

欢迎提Issue和PR！详见 [CONTRIBUTING.md](CONTRIBUTING.md)

## License

MIT
