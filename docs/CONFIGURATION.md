# Configuration reference

Generated from `new-bots/options/.env.example`. Copy the template, never another person's `.env`. Template defaults are starting settings, not account/risk recommendations. Read its comments and source before changing a safety control.

| Variable | Template default | Role |
| --- | --- | --- |
| `DISCORD_TOKEN` | your own value; optional when its source is disabled | Private credential from your own account/application. |
| `DISCORD_CLIENT_ID` | your own value; optional when its source is disabled | Your own server/application/account identifier. |
| `DISCORD_GUILD_ID` | your own value; optional when its source is disabled | Your own server/application/account identifier. |
| `DISCORD_CHANNEL_ID` | your own value; optional when its source is disabled | Your own server/application/account identifier. |
| `DISCORD_DELIVERY_MODE` | bot | Runtime, data-source, cost, review or safety setting; see template comments. |
| `SCAN_TIMEOUT_MINUTES` | 20 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_SESSION_FILE` | examples/paper-session.json | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_SOURCE` | manual | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_DISCOVERY_SOURCE` | auto | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_DISCOVERY_FEED` | iex | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_DISCOVERY_MAX_CANDIDATES` | 12 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_DISCOVERY_MAX_QUOTE_AGE_MS` | 15000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_DIRECTORY_REFRESH_MS` | 21600000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_DIRECTORY_CACHE_PATH` | .cache/options-underlying-directory.json | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_DISCOVERY_HISTORY_PATH` | .cache/options-discovery-history | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_INTRADAY_RESEARCH_SOURCE` | auto | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_INTRADAY_RESEARCH_MAX_UNDERLYINGS` | 12 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_INTRADAY_RESEARCH_BUDGET_MS` | 45000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_INTRADAY_RESEARCH_HISTORY_PATH` | .cache/options-intraday-research | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_INDEPENDENT_PAPER_SOURCE` | auto | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_INDEPENDENT_PAPER_MAX_UNDERLYINGS` | 3 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_INDEPENDENT_PAPER_BUDGET_MS` | 45000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CONTRACT_DISCOVERY_SOURCE` | auto | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CONTRACT_MAX_UNDERLYINGS` | 12 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CONTRACT_MAX_EXPIRATIONS` | 2 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CONTRACT_MIN_DTE` | 1 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CONTRACT_MAX_DTE` | 45 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CONTRACT_BUDGET_MS` | 45000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_EXPIRATION_REFRESH_MS` | 3600000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_EXPIRATION_CACHE_PATH` | .cache/options-expirations | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CONTRACT_HISTORY_PATH` | .cache/options-contract-history | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_SIGNAL_SOURCE` | manual | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_PRIMARY_SIGNAL_MAX_AGE_MS` | 120000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CATALYST_REVIEW_FILE` | examples/catalyst-reviews.json | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CATALYST_REVIEW_MAX_AGE_MS` | 1800000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_ASSIGNMENT_REVIEW_MAX_AGE_MS` | 86400000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_ASSIGNMENT_DATA_SOURCE` | manual | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_CATALYST_SOURCE` | manual | Runtime, data-source, cost, review or safety setting; see template comments. |
| `FINNHUB_API_KEY` | your own value; optional when its source is disabled | Private credential from your own account/application. |
| `ALPACA_API_KEY_ID` | your own value; optional when its source is disabled | Private credential from your own account/application. |
| `ALPACA_API_SECRET_KEY` | your own value; optional when its source is disabled | Private credential from your own account/application. |
| `TRADIER_ENV` | sandbox | Runtime, data-source, cost, review or safety setting; see template comments. |
| `TRADIER_TOKEN` | your own value; optional when its source is disabled | Private credential from your own account/application. |
| `TRADIER_PRODUCTION_REQUESTS_PER_MINUTE` | 108 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `TRADIER_SANDBOX_REQUESTS_PER_MINUTE` | 54 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `TRADIER_SHARED_RATE_DIR` | (empty; review before enabling) | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_QUOTE_AGE_MS` | 10000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_OPEN_MARK_AGE_MS` | 300000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `PAPER_ACCOUNT_EQUITY_USD` | (empty; review before enabling) | Runtime, data-source, cost, review or safety setting; see template comments. |
| `TRADING_RISK_STATE_PATH` | (empty; review before enabling) | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OMNIMOD_EMERGENCY_STOP` | true | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OMNIMOD_LIVE_TRADING_ENABLED` | false | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_QUOTE_AGE_MS` | 10000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_LEG_SKEW_MS` | 3000 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_LEG_SPREAD_PCT` | 15 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_COMBO_SPREAD_PCT` | 25 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MIN_OPEN_INTEREST` | 100 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MIN_VOLUME` | 1 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MIN_DTE` | 1 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_DTE` | 45 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_FORCE_EXIT_BUFFER_MINUTES` | 5 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MIN_REWARD_RISK` | 1.5 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_FEES_PER_CONTRACT_ROUND_TRIP` | (empty; review before enabling) | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_SLIPPAGE_RESERVE_PER_CONTRACT` | (empty; review before enabling) | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_TRADE_RISK_PCT` | 0.25 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_TOTAL_OPEN_RISK_PCT` | 1 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_GROSS_EXPOSURE_PCT` | 100 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `OPTIONS_MAX_DAILY_LOSS_PCT` | 1 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `SCAN_INTERVAL_MINUTES` | 2 | Runtime, data-source, cost, review or safety setting; see template comments. |
| `DISCORD_WEBHOOK_URL` | (empty; review before enabling) | Runtime, data-source, cost, review or safety setting; see template comments. |
| `PAPER_MONITOR_INTERVAL_SECONDS` | 0 | Runtime, data-source, cost, review or safety setting; see template comments. |
