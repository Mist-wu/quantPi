# Docs

- DefiLlama API docs/api-sources.md
- duckduckgo_search https://raw.githubusercontent.com/deedy5/ddgs/refs/heads/main/README.md
- Binance https://developers.binance.com/docs/derivatives/usds-margined-futures/general-info
- Fred https://raw.githubusercontent.com/mortada/fredapi/refs/heads/master/README.md
- Tavily AI docs https://docs.tavily.com/llms.txt
- Newsapi https://newsapi.org/docs

# RSS

## 币圈实时新闻

- CoinDesk RSS: https://www.coindesk.com/arc/outboundfeeds/rss/
- CoinTelegraph RSS: https://cointelegraph.com/rss

## 权威宏观与全球时事

- 华尔街日报 (WSJ) 核心新闻: https://feeds.a.dj.com/rss/WSJcomUSBusiness.xml
- FT 中文网: http://www.ftchinese.com/rss/feed



# 日志与复盘

每次新闻因子、策略分数、风控结果、下单请求都写入 SQLite 或 JSONL。

学习之前市场。

# Pi

Pi documentation (read only when the user asks about pi itself, its SDK, extensions, themes, skills, or TUI):
- Main documentation: /Users/wu/.nvm/versions/node/v24.14.0/lib/node_modules/@earendil-works/pi-coding-agent/README.md
- Additional docs: /Users/wu/.nvm/versions/node/v24.14.0/lib/node_modules/@earendil-works/pi-coding-agent/docs
- Examples: /Users/wu/.nvm/versions/node/v24.14.0/lib/node_modules/@earendil-works/pi-coding-agent/examples (extensions, custom tools, SDK)
- When reading pi docs or examples, resolve docs/... under Additional docs and examples/... under Examples, not the current working directory
- When asked about: extensions (docs/extensions.md, examples/extensions/), themes (docs/themes.md), skills (docs/skills.md), prompt templates (docs/prompt-templates.md), TUI components (docs/tui.md), keybindings (docs/keybindings.md), SDK integrations (docs/sdk.md), custom providers (docs/custom-provider.md), adding models (docs/models.md), pi packages (docs/packages.md)
- When working on pi topics, read the docs and examples, and follow .md cross-references before implementing
- Always read pi .md files completely and follow links to related docs (e.g., tui.md for TUI API details)