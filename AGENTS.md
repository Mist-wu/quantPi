# AI阅读的本项目指南

## 项目结构

```text
CryptoPilot/
  cryptopilot/
    __init__.py
    config.py          # 读取 .env、配置
    models.py          # Pydantic 数据模型
    sources/           # 数据源
      binance.py
      defillama.py
      fred.py
      newsapi.py
      tavily.py
      ddgs.py
    factors/           # AI 新闻/宏观因子提取
      news_factor.py
      macro_factor.py
    strategy/          # 打分和交易决策
      scoring.py
      rules.py
    risk/              # 风控
      circuit_breaker.py
      position_limits.py
    broker/            # 下单执行
      binance_futures.py
    storage/           # SQLite / DuckDB / JSONL
      db.py
    cli.py             # 命令行入口
  tests/
  .env
  pyproject.toml
  README.md
```

## 技术栈

| 工具 | 用途 |
| --- | --- |
| uv | 包管理 / 运行 |
| pydantic | 配置和数据校验 |
| httpx | API 请求 |
| pandas | 行情和指标计算 |
| ccxt | 交易所接口（可选） |
| sqlalchemy | SQLite 存储（可选） |
| typer | 命令行工具 |
| rich | 终端美化 |
| pytest | 测试 |
| ruff | 格式化和 lint |

## 构建

### Docs

- DefiLlama API docs/api-sources.md
- duckduckgo_search https://raw.githubusercontent.com/deedy5/ddgs/refs/heads/main/README.md
- Binance https://developers.binance.com/docs/derivatives/usds-margined-futures/general-info
- Fred https://raw.githubusercontent.com/mortada/fredapi/refs/heads/master/README.md
- Tavily AI docs https://docs.tavily.com/llms.txt
- Newsapi https://newsapi.org/docs

### RSS

#### 币圈实时新闻

- CoinDesk RSS: https://www.coindesk.com/arc/outboundfeeds/rss/
- CoinTelegraph RSS: https://cointelegraph.com/rss

#### 权威宏观与全球时事

- 华尔街日报 (WSJ) 核心新闻: https://feeds.a.dj.com/rss/WSJcomUSBusiness.xml
- FT 中文网: http://www.ftchinese.com/rss/feed

### 最小启动路线

```text
第 1 步：搭项目骨架 + pyproject.toml
第 2 步：封装 Binance / DefiLlama / FRED / NewsAPI / Tavily / DDGS
第 3 步：做 check-sources 命令
第 4 步：做 scan 命令，输出市场快照
第 5 步：做 scoring.py，计算总分
第 6 步：做 dry-run 交易决策
第 7 步：加风控和真实下单
```

## 运行

本项目为 CLI 工具：

```bash
# 测试所有 API
cryptopilot check-sources

# 查看账户和持仓
cryptopilot account

# 拉取 ETHUSDT 行情和新闻
cryptopilot scan ETHUSDT

# 只计算信号，不下单
cryptopilot decide ETHUSDT --dry-run

# 自动运行
cryptopilot run --symbols BTCUSDT,ETHUSDT --interval 5m
```

## 测试

## 日志与复盘

每次新闻因子、策略分数、风控结果、下单请求都写入 SQLite 或 JSONL。

学习之前市场。
