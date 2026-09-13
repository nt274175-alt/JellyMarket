# Jelly Market 3.0 — Complete Live Edition

Jelly Market is a **read-only Android market dashboard** for NIFTY 50 and BANK NIFTY using Angel One SmartAPI. This release combines the live feed, REST fallback, historical seed, technical engine, news sentiment, chart, Hindi voice, lifecycle handling, reconnect/watchdog and GitHub Actions build into one final source package.

## What is included
- Angel One login: API Key + Client ID + current PIN + TOTP
- API Key and Client ID stored locally; PIN/TOTP are never saved
- Live SmartAPI WebSocket 2.0
- NIFTY WebSocket token `26000`
- BANK NIFTY WebSocket token `26009`
- REST quote/historical token separation: NIFTY `99926000`, BANK NIFTY `99926009`
- WebSocket heartbeat every 30 seconds
- Stale-feed watchdog and exponential reconnect
- REST quote fallback every 15 seconds while active
- Recent 1-minute historical candle seed for EMA/RSI/momentum
- EMA20 + RSI14 + short-term momentum
- Combined BULLISH / BEARISH / SIDEWAYS view
- BUY BIAS / SELL BIAS / WAIT-HOLD signal with confidence score
- Support/resistance snapshot
- Live score chart
- Google News RSS headlines + simple keyword sentiment
- Hindi text-to-speech summary
- Market-hours guard (NSE weekdays 09:15–15:30)
- Activity pause/resume lifecycle protection
- Logout/session cleanup
- Source sanity checks
- GitHub Actions debug APK + SHA-256 artifact

## Important safety note
Jelly Market **does not place trades**. Its signal is a rule-based technical indicator, not a guaranteed prediction or financial advice. Never share your Angel One API key, PIN, TOTP or tokens.

## Build the APK
1. Upload this project to a GitHub repository.
2. Push to the `main` branch, or open **Actions → Build Jelly APK → Run workflow**.
3. The workflow installs JDK 17, Gradle 8.7 and Android SDK 35.
4. Download the `JellyMarket-debug-apk` artifact and install `app-debug.apk` on the Android phone.

## Local build
Android SDK + Gradle are required. The included `build-apk.sh` runs `gradle --no-daemon :app:assembleDebug`.

## Angel One connection
SmartAPI's current WebSocket 2.0 endpoint is `wss://smartapisocket.angelone.in/smart-stream`. The app uses the documented authentication headers and 30-second heartbeat.

## Version
**3.0-complete / versionCode 20**
