# OmniMod Options Bot

Research defined-risk debit verticals with contract-specific pricing and independent underlying/option gates. `npm start` launches **only Options**. Automated tests establish code behavior; current provider coverage and forward performance require separate evidence.

## How it works

1. Consume fresh delivered Stocks/ETF hypotheses in shared-signal mode while retaining original entry zone, target, stop and deadline. Independent discovery is a separate research track.
2. Discover supported underlyings/contracts with capped deeper chain work; resolve exact OCC identity, expiry, strike, type and both legs.
3. Require the underlying strategy, synchronized underlying/leg quotes, liquidity, spread, catalyst and assignment/dividend evidence.
4. Evaluate the two-leg debit, multiplier, explicit costs, maximum loss, portfolio exposure and pending-entry evidence.
5. Recheck current underlying invalidation, both legs, catalysts/session and shared risk at later-quote fill; monitor exact stored legs afterward.

Highlights are not the full universe and watches are not automatically approved entries. Model probability, heuristic strength and data quality have different meanings. Zero results can mean a closed session, disabled provider, missing evidence, pending model or risk rejection.

## Requirements and layout

Use Git, **Node.js 22.9+** (the export was checked with Node 24), npm and your own Discord app/server. The primary project is [`new-bots/options/`](new-bots/options/). The existing six-market source integration bundle is preserved because shared adapters/tests import sibling projects. Their presence does not start those bots. The root wrapper selects only this repository’s named application.

`repository.json` records the original export/source hashes. Later Git commits/tags are authoritative for subsequent changes. Dependencies remain locked in the existing project lockfiles.

## Install from a clean checkout

```sh
git clone https://github.com/MercyProductions/OmniMod-Options-Bot.git
cd OmniMod-Options-Bot
npm run bootstrap
npm run info
npm test
npm run check
```

Bootstrap installs locked dependencies with lifecycle scripts disabled. It does not create a provider subscription. Tests use isolated fixture/mocked inputs.

Copy the template on Windows PowerShell:

```powershell
Copy-Item new-bots/options/.env.example new-bots/options/.env
```

Or on Linux/macOS:

```sh
cp new-bots/options/.env.example new-bots/options/.env
```

Edit that **local** `.env`; never copy the maintainer’s tokens or publish your file. [Every shipped template setting is listed here](docs/CONFIGURATION.md), with sensitive values replaced by instructions to supply your own.

## Create your own Discord application

1. In the [Developer Portal](https://discord.com/developers/applications), create your own application and bot user. Choose its name/avatar.
2. Reset/copy its bot token into `DISCORD_TOKEN`; set the application ID as `DISCORD_CLIENT_ID`. They are different values. Each independently running bot needs its own application/token.
3. Enable Discord Developer Mode and copy your server ID to `DISCORD_GUILD_ID`. Configure DISCORD_CHANNEL_ID; never reuse the owner’s destination IDs.
4. Install it to your server with `bot` and `applications.commands` scopes. Allow View Channel, Send Messages, Embed Links and Read Message History in its channels. Setup that creates channels/roles needs the corresponding management permission.
5. Register commands and start this application:

```sh
npm run register
npm start
```

For this app, `npm --prefix new-bots/options run setup` exposes its setup workflow after guild/channel configuration. Registration/startup connects to your own Discord application and can publish messages. A connected gateway does not establish feed readiness.

The identity skeleton is deliberately empty:

```dotenv
DISCORD_TOKEN=
DISCORD_CLIENT_ID=
DISCORD_GUILD_ID=
```

Add the project’s own destination/provider fields from its template. Do not share tokens in issues, screenshots or pull requests.

## Free data and paid upgrades

| Source | Role | Settings in local .env | Limits / prerequisites |
| --- | --- | --- | --- |
| Manual examples | Free offline setup | OPTIONS_SOURCE=manual | Fixtures are not a current chain scan. |
| Tradier Sandbox | Delayed account-based research | OPTIONS_SOURCE=tradier; TRADIER_ENV=sandbox; TRADIER_TOKEN | Delayed sandbox quotes cannot meet the strict fresh-entry gate. |
| Tradier Production data | Account/entitlement-based fresh data | TRADIER_ENV=production; your TRADIER_TOKEN | Selects a data endpoint, not order execution. Confirm personal-use/data permissions. |
| Alpaca underlying data | Optional free IEX/entitled SIP discovery | ALPACA_API_KEY_ID; ALPACA_API_SECRET_KEY; OPTIONS_DISCOVERY_SOURCE=alpaca; OPTIONS_DISCOVERY_FEED=iex or sip | Underlying observations do not replace exact option-leg data. |
| Catalyst/assignment reviews | Manual or optional enrichment | OPTIONS_CATALYST_REVIEW_FILE; OPTIONS_ASSIGNMENT_DATA_SOURCE; FINNHUB_API_KEY | Missing/stale review evidence cannot clear an actual candidate. |

Review this mode skeleton; blank credentials intentionally do not authenticate:

```dotenv
OPTIONS_SOURCE=manual
TRADIER_ENV=sandbox
TRADIER_TOKEN=
OPTIONS_SIGNAL_SOURCE=manual
OMNIMOD_EMERGENCY_STOP=true
OMNIMOD_LIVE_TRADING_ENABLED=false
```

The [configuration reference](docs/CONFIGURATION.md) lists all shipped variables. A key enables only the implemented adapters, not every endpoint sold by the provider. Read the primary project’s [existing technical guide](new-bots/options/README.md) for deeper settings and market-specific workflows.

### Preview provider profiles

```sh
npm --prefix new-bots run data:setup -- --bot options --profile free
npm --prefix new-bots run data:setup -- --list
```

Without `--apply`, this previews settings/missing prerequisites without editing `.env` or calling a provider. A free profile can be unsupported (Futures) or observation-only (limited/delayed feeds). Upgrade names differ by bot: inspect `--list` rather than assuming every market has a `paid` profile. Use `--apply` only after adding your own credentials and reviewing selectors. Equity, cost reserves, contract reviews and catalysts still require configuration.

## Paper accounts and shared risk

No live order route is implemented. Keep `OMNIMOD_LIVE_TRADING_ENABLED=false`. The emergency stop defaults to true. For paper reservations, deliberately configure positive paper equity, instrument-specific fees/slippage, current catalyst evidence and reviewed risk limits before setting `OMNIMOD_EMERGENCY_STOP=false`.

Stocks/Crypto use `OMNIMOD_PAPER_ACCOUNT_EQUITY_USD`; the other four bots use `PAPER_ACCOUNT_EQUITY_USD`. The first reservation anchors that ledger’s equity. A missing validated model, quote, review, cost assumption or account basis can block entries while discovery still operates.

For multiple clones on one computer, set the **same absolute `TRADING_RISK_STATE_PATH` and `OMNIMOD_SIGNAL_RESEARCH_PATH`** in every participating bot’s private configuration. Separate clones have separate default portfolios. Match equity/cost assumptions and keep marks current. File locks do not coordinate different hosts. Shared research never overrides the primary owner’s strategy/risk approval.

Watch, reservation, fill and target-hit counts have different meanings. Paper entry requires a later eligible quote. Stops/targets/excursions/returns are quote-sampled simulations after recorded costs, not calibrated broker fills. See [shared risk](new-bots/shared/paperRisk.js) and [fill checks](new-bots/shared/FILL_PORTFOLIO_RISK.md).

## Configure an account step by step

Obtain a Sandbox token from your own Tradier developer/account access for delayed testing. Use `OPTIONS_SOURCE=tradier` with `TRADIER_ENV=sandbox`, and expect the fresh-entry gate to reject delayed observations. For current production market data obtain the appropriate own-account token/entitlement and select `TRADIER_ENV=production`; the code still uses data endpoints and paper accounting. For `OPTIONS_SIGNAL_SOURCE=shared`, run your own Stocks/ETF publishers with a common absolute research-journal path; no primary signals means no shared-mode source opportunities. Independent discovery requires its own Alpaca settings and remains a distinct research track. Prepare the current catalyst and assignment/dividend reviews from actual sources; shipped examples are not current evidence.

## Operation and diagnostics

/options help and /options status. Separate zero primary signals, provider-ready underlyings, strategy rejections and risk rejections.

Additional commands from this repository root:

```sh
npm --prefix new-bots/options run probe:universe
npm --prefix new-bots/options run scan
```

Probes/scans can contact the configured provider; metered history or explicit odds refresh may consume your credits. Review request/cost caps first. Do not start duplicate workers against one Discord identity/data store.

| Symptom | Check |
| --- | --- |
| No slash commands | Own token/client-ID pair, correct guild installation, registration and permissions. |
| Connected but zero candidates | Selected source, discovery/screen counts, session, current inputs and rejected-gate reasons. |
| HTTP 401/403 | Key validity, account region/permissions and endpoint entitlement; do not report it as no opportunities. |
| HTTP 429 | Quota headers, cooldown/concurrency and duplicate workers sharing the same provider account. |
| Watches without setups | Data age, model readiness, confirmation, catalyst evidence, explicit costs, emergency stop and risk limits. |
| Unexpected result summary | Separate research/shadow observations, issued alerts, delivery and actual paper fills. Consult durable records. |
| Stale records after restart | Actual data path/OS user, timezone, last successful request and old state; preserve the store when investigating. |

Runtime stores can contain private server settings and credentials saved by admin commands. Keep them outside Git/public web roots, persist them across restarts and back them up privately before upgrades. Original hosting documents may describe older deployments; source publication does not configure cPanel or start a production service.

## Baseline and contributing

The pre-change version is preserved as [`baseline/pre-readme-sports-audit-2026-10-20`](https://github.com/MercyProductions/OmniMod-Options-Bot/tree/baseline/pre-readme-sports-audit-2026-10-20), commit `8dd30b09d16da9af5401741a8b58fdeaa7af0b47`. Inspect it without erasing later work:

```sh
git switch -c inspect-baseline baseline/pre-readme-sports-audit-2026-10-20
```

Fork, create a development branch and use your own local credentials. Add regression tests for confirmed defects. Freeze model/strategy versions, dates, horizons and costs before evaluating changes. Compare the same chronological out-of-sample game/trade populations, reporting proper scores/calibration, sample sizes, costs and unresolved outcomes. A few good days or more alerts do not establish improvement. Preserve source and private runtime evidence before model changes.

`npm test` runs this primary project’s tests. `npm run check` runs configured syntax checks. `npm run test:all` checks the full shared/new-market, Stocks and Crypto integration bundle. Submit the problem/change/checks/limits in your PR; share sanitized diagnostics rather than private state.

## Source map

- [Strategy](new-bots/options/src/strategies.js)
- [Fill evidence](new-bots/options/FILL_EVIDENCE.md)
- [Frozen hypotheses](new-bots/options/PRIMARY_HYPOTHESIS.md)

## Provider documentation

- [Discord setup](https://docs.discord.com/developers/quick-start/getting-started)
- [Alpaca coverage](https://docs.alpaca.markets/us/docs/about-market-data-api)
- [CoinGecko Demo authentication](https://docs.coingecko.com/demo/reference/authentication)
- [OANDA API access](https://developer.oanda.com/rest-live-v20/introduction/)
- [Databento access](https://databento.com/docs/getting-started/build-first-app)
- [Tradier sandbox/data differences](https://docs.tradier.com/docs/market-data)
- [The Odds API v4](https://the-odds-api.com/liveapi/guides/v4/)

References checked on 2026-10-20. Confirm current region, licensing, quota and endpoint entitlement in your own account before enabling a paid selector. Each contributor needs their own provider account; this code does not redistribute the maintainer’s data subscriptions.
