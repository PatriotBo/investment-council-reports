# Investment Council · 投研圆桌报告归档

> 14 Agent · 5 Phase · 多空辩论 · 三向风控 · 组合经理终裁 —— 本地化多智能体投研系统产出的深度研判报告归档站点。

🌐 **在线访问**：https://patriotbo.github.io/investment-council-reports/

---

## 📦 这是什么

Investment Council 是一个本地化的 14 智能体投研圆桌系统，由宿主 LLM 顺序扮演 6 大分析师 + 多头/空头研究员 + 研究总监 + 交易员 + 三方风控 + 组合经理共 14 个角色，对单只标的（A 股 / 港股 / 美股 / ETF / 可转债 / 指数）产出带置信度、目标价、止损价、仓位建议的结构化决策报告。

本仓库归档由该系统产出的所有 HTML 报告。

每份报告包含：
- 🎯 **三段式决策总览**：执行摘要 + 5 维评分 + 决策路径流转图
- 🔬 **Phase 1 · 六大分析师并行视角**：基本面 / 技术 / 情绪 / 新闻 / 宏观 / 资金
- ⚔️ **Phase 2 · 多空辩论**：7 Claim 对决 + 研究总监仲裁
- 💼 **Phase 3-5 · 交易员落地方案 + 三方风控博弈**
- 🎩 **Phase 6 · 组合经理终裁** + 结构化决策卡 JSON
- 📖 **末尾术语表**：PE_TTM / MACD / RSI / CAPEX 等专业术语 hover tooltip + 锚点跳转

---

## 🗂️ 目录结构

```
.
├── index.html          # 报告归档首页（带搜索 / 筛选 / 卡片网格）
├── manifest.json       # 报告元数据清单（前端动态加载）
├── reports/            # 所有 HTML 报告
│   └── {code}-{exchange}-{date}.html
├── .nojekyll           # 禁用 Jekyll 处理
└── README.md
```

---

## ➕ 如何添加新报告

1. 把新生成的 HTML 报告（来自本地 `~/investment-council/reports/`）拷贝到 `reports/` 目录
2. 在 `manifest.json` 的 `reports` 数组里追加一条元数据：

```json
{
  "code": "600519",
  "suffix": "SH",
  "name": "贵州茅台",
  "market": "A股",
  "industry": "白酒 / 高端消费",
  "date": "2026-06-01",
  "decision": "HOLD",
  "confidence": 65,
  "current_price": 1620.00,
  "target_t1": 1750,
  "target_t2": 1900,
  "stop_loss": 1500,
  "summary": "一句话讲完为啥这个决策...",
  "file": "reports/600519-SH-2026-06-01.html"
}
```

3. `git add . && git commit -m "Add: 贵州茅台 2026-06-01" && git push`
4. GitHub Pages 自动重新部署（约 30-90 秒）

---

## ⚖️ 免责声明

本仓库所有报告由 Investment Council 多智能体系统基于公开数据自动生成，**仅供研究讨论与教育用途**：

- 不构成任何投资建议
- 不保证准确性
- 不替代专业投顾

投资有风险，决策请自行承担。

---

## 📄 许可

- 报告内容：CC BY-NC-SA 4.0（署名 - 非商业 - 相同方式共享）
- 站点代码：MIT
