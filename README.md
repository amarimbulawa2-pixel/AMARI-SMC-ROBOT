# AMARI SMC ROBOT — Android prototype v0.1.0

## What this prototype does
- Android dashboard built with Kotlin and Jetpack Compose.
- Three market tabs: Pain X, Gain X and Gold.
- Local illustrative OHLC sample data.
- First-pass SMC scanner: pivot swing points, close-based structure breaks,
  simple liquidity-sweep candidates and three-candle FVG candidates.
- Start/stop control for the local sample scanner and a configurable risk display.

## What it does NOT do
- It is not connected to Weltrade, MT5, TradingView or any live market feed.
- It does not submit, modify or close orders.
- It does not calculate broker-valid lot sizes, margin, tick values or contract sizes.
- It does not provide validated trading signals. Any BUY SETUP / SELL SETUP is
  an educational candidate, not a recommendation to trade.
- The START switch only changes the local prototype UI state; it does not start
  a persistent background service.

## Open in Android Studio
1. Install Android Studio with Android SDK 35.
2. Open this folder as an existing Gradle project.
3. Allow Gradle sync to complete.
4. Run the `app` configuration on an Android 8.0+ device or emulator.

The project uses Android Gradle Plugin 8.7.3, Kotlin 2.0.21 and Compose BOM
2024.12.01. Android Studio may offer a compatible Gradle wrapper if one is absent.

## Next engineering milestones
1. Verify Weltrade's permitted MT5 automation / API route and symbol specifications.
2. Implement candle ingestion with timestamps, bid/ask, spread and completed-bar handling.
3. Replace prototype pivots with configurable, testable BOS/CHoCH definitions.
4. Add higher-timeframe bias (1H), setup timeframe (15M), entry timeframe (5M),
   FVG retracement and order-block validation.
5. Build historical replay/backtesting with spread, slippage, commission and
   realistic execution assumptions.
6. Add a demo-only execution adapter, idempotent order handling, kill switch,
   daily loss lockout and audit logs.
7. Validate on a demo account over a sufficiently large sample before considering
   any live trading capability.

## Safety defaults
Demo only. No broker credentials are requested or stored. No order execution code
is included. Do not add live trading until the broker connection and risk controls
have been independently tested.
