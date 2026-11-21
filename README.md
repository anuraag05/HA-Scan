# NSE Close vs Heikin-Ashi Scan (Dhan + Streamlit)

For every NSE stock and timeframe (1m, 5m, 15m, 30m, 1H, 1D) shows **Up** when the
regular candle close is above the Heikin-Ashi close and **Down** when it is below,
with summary and per-stock charts (regular candles, Heikin-Ashi candles, and the difference).

## Deploy on Streamlit Community Cloud
1. Push this repo to GitHub.
2. share.streamlit.io -> New app -> this repo, branch `main`, file `app.py`.
3. Advanced settings -> Secrets:
   ```toml
   DHAN_CLIENT_ID = "your-client-id"
   DHAN_ACCESS_TOKEN = "your-access-token"
   ```
4. Update the token in Secrets when it expires (or paste a temporary one in the sidebar).

## Notes
- 15m, 30m and 1H candles are built from 5m data; each stock needs up to 3 Dhan calls.
- Dhan data API is limited to 5 requests/sec; the app stays at ~2.5/sec. Start with Nifty 50/100.
