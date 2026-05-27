# 贡献指南

欢迎为 anti-hallucination 贡献！

## 怎么贡献

### 提建议（Issue）

1. 在 [Issues](https://github.com/qianmao1989/anti-hallucination/issues) 页面提交
2. 选对应的模板（Bug报告 / 功能建议 / 改进想法）
3. 描述清楚你的场景和预期效果

### 提代码（Pull Request）

1. Fork 本仓库
2. 创建你的分支：`git checkout -b feature/你的功能名`
3. 改完后提交：`git commit -m "描述你改了什么"`
4. 推送到你的分支：`git push origin feature/你的功能名`
5. 提 Pull Request，说明改了什么、为什么改

### 改什么有用

- 补充禁止词库（中英文都欢迎）
- 新增验证模式（比如新语言的代码检测）
- 修bug
- 改进文档
- 增加测试用例
- 翻译改进

## 规则

- 一个PR做一件事，不要混杂多个改动
- PR描述要写清楚改了什么、为什么改
- 代码风格保持和现有文件一致
- 不确定的想法先开Issue讨论，别直接提PR

## 目录结构

```
anti-hallucination/
├── SKILL.md                    # 核心规则
├── ARTICLE.md                  # 项目故事
├── rules/                      # 详细规则
├── hooks/                      # 钩子机制
├── scripts/                    # 可执行脚本
├── assets/                     # 模板
└── CONTRIBUTING.md             # 你正在看的这个
```
