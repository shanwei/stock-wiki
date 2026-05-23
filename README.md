# Stock Wiki | 股票投研维基

[English](#english) | [中文](#中文)

---

## 中文

一个由 LLM（Claude）自动维护的个人股票投研知识库，遵循 [Karpathy LLM Wiki](https://x.com/karpathy/status/1928070335855356109) 理念——**将原始资料（年报、研报、公告）转化为结构化、可决策、可追溯的投研内容**。

### 核心理念

- **raw/ 只读，wiki/ 只写**——原始资料放入 `raw/` 目录（gitignored），LLM 自动读取并生成 `wiki/` 页面，人类不手动编辑 wiki
- **内容必须可追溯**——所有 wiki 内容基于 raw/ 原始资料，不编造、不夸大，每页标注资料来源
- **多市场适配**——统一框架覆盖 A 股、港股、美股，自动适配不同市场的财务口径和估值逻辑
- **Obsidian 友好**——使用 `[[wikilink]]` 内部链接，可用 Obsidian 直接浏览全库

### 覆盖范围

| 类别 | 数量 | 示例 |
|------|------|------|
| A 股 | 11 只 | 宁德时代、寒武纪、中际旭创、阳光电源、澜起科技、天孚通信... |
| 港股 | 6 只 | 腾讯控股、小米集团、泡泡玛特、蜜雪集团、智谱、MiniMax |
| 美股 | 6 只 | 英伟达、台积电、ASML、谷歌、Coherent、Lumentum |
| 行业 | 4 个 | 新能源、AI、消费、创新药 |
| 宏观 | 1 个 | 全球宏观事件、利率周期、资产配置 |

### 目录结构

```
stock-wiki/
├── 00_宏观/              # 宏观经济分析
│   ├── raw/              # 原始资料（gitignored）
│   └── wiki/             # LLM 生成的宏观分析
├── 01_行业_新能源/        # 行业分析（4个行业）
├── 02_行业_AI/
├── 03_行业_消费/
├── 04_行业_创新药/
├── A股_宁德时代_300750/   # 每只股票独立目录
│   ├── raw/              # 年报、季报、研报（gitignored）
│   └── wiki/             # 6 页标准 wiki
│       ├── 公司核心分析.md
│       ├── 财务分析.md
│       ├── 估值分析.md
│       ├── 催化剂与风险点.md
│       ├── 公告与纪要总结.md
│       └── index.md
├── 港股_腾讯控股_00700/
├── 美股_英伟达_NVDA/
├── index.md              # 全局索引
├── log.md                # 操作日志
├── CLAUDE.md             # LLM 规则文件
└── README.md
```

### 标准化的 Wiki 页面（每只股票 6 页）

| 页面 | 内容 |
|------|------|
| 公司核心分析 | 主营业务、护城河、管理层、行业地位、竞品对比 |
| 财务分析 | 3-5 年核心指标表、财务亮点与风险、同行对比 |
| 估值分析 | PE/PB/ROE、估值逻辑、合理估值区间 |
| 催化剂与风险点 | 核心催化剂、风险因素、影响程度矩阵 |
| 公告与纪要总结 | 按时间倒序，年报/季报/重大公告核心要点 |
| index | 页面索引 + 行业/竞品关联链接 |

### 技术栈

- **LLM**：Claude (Claude Code CLI)
- **存储**：Markdown 文件，Git 版本控制
- **浏览**：Obsidian / 任意 Markdown 编辑器
- **数据源**：巨潮资讯网、港交所披露易、SEC EDGAR、券商研报

---

## English

A personal stock research knowledge base automatically maintained by an LLM (Claude), following the [Karpathy LLM Wiki](https://x.com/karpathy/status/1928070335855356109) philosophy—**transforming raw materials (annual reports, research, filings) into structured, actionable, and traceable investment research content**.

### Core Principles

- **raw/ is read-only, wiki/ is LLM-write-only** — source materials go into `raw/` (gitignored), the LLM reads them and generates `wiki/` pages; humans never manually edit wiki
- **Everything is traceable** — all wiki content is derived from raw/ sources, no fabrication or exaggeration, every page cites its sources
- **Multi-market support** — unified framework covering A-shares, HK stocks, and US stocks, automatically adapting to different accounting standards and valuation logics
- **Obsidian friendly** — uses `[[wikilink]]` internal links, browse the entire vault with Obsidian

### Coverage

| Category | Count | Examples |
|----------|-------|---------|
| A-shares | 11 | CATL, Cambricon, Zhongji Innolight, Sungrow, Montage Tech, Tianfu Comm... |
| HK Stocks | 6 | Tencent, Xiaomi, Pop Mart, Mixue, Zhipu, MiniMax |
| US Stocks | 6 | NVIDIA, TSMC, ASML, Google, Coherent, Lumentum |
| Industries | 4 | New Energy, AI, Consumer, Biotech |
| Macro | 1 | Global macro events, rate cycles, asset allocation |

### Directory Structure

```
stock-wiki/
├── 00_宏观/              # Macro analysis
│   ├── raw/              # Source materials (gitignored)
│   └── wiki/             # LLM-generated macro analysis
├── 01_行业_新能源/        # Industry analysis (4 industries)
├── 02_行业_AI/
├── 03_行业_消费/
├── 04_行业_创新药/
├── A股_宁德时代_300750/   # Each stock has its own directory
│   ├── raw/              # Annual/quarterly reports, research (gitignored)
│   └── wiki/             # 6 standard wiki pages
│       ├── 公司核心分析.md  # Core company analysis
│       ├── 财务分析.md      # Financial analysis
│       ├── 估值分析.md      # Valuation analysis
│       ├── 催化剂与风险点.md # Catalysts & risks
│       ├── 公告与纪要总结.md # Filings & meeting summaries
│       └── index.md        # Page index + related links
├── 港股_腾讯控股_00700/
├── 美股_英伟达_NVDA/
├── index.md              # Global index
├── log.md                # Operation log
├── CLAUDE.md             # LLM rules
└── README.md
```

### Standardized Wiki Pages (6 per stock)

| Page | Content |
|------|---------|
| Core Analysis | Business segments, moats, management, industry position, competitor comparison |
| Financial Analysis | 3-5 year key metrics, highlights & risks, peer comparison |
| Valuation Analysis | PE/PB/ROE, valuation logic, fair value range |
| Catalysts & Risks | Key catalysts, risk factors, impact matrix |
| Filings Summary | Chronological summary of annual/quarterly reports and major announcements |
| Index | Page index + cross-references to industry/peers |

### Tech Stack

- **LLM**: Claude (Claude Code CLI)
- **Storage**: Markdown files, Git version control
- **Browsing**: Obsidian / any Markdown editor
- **Data Sources**: CNINFO, HKEX HKDNews, SEC EDGAR, broker research reports
