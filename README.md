# Hadès V3.1 — Public Audit Trail

BTC active risk management strategy · **forward paper test from 2026-04-15** · review **2026-10-15** (6 months min).

**0 client capital deployed.** All snapshots below are forward paper test on real-time BTC market data with frozen V3.1 parameters. No broker capital is at risk.

## What this proves

- **SHA-256 integrity hashes** verify the strategy engine files have not changed since genesis (2026-04-15).
- **Drift reports** show forward-paper performance vs backtest expected (Harvey-Liu 2015 haircut).
- **Daily snapshots** are append-only commits — every line in the table below is a separate cron run.

## What this never publishes

- BUY/SELL signal names (entry/exit conditions stay proprietary)
- Scale-in / drawdown stop / regime parameters (specific values)
- Cooldown periods, friction model details

## Reference claims (source: claims_sheet.md authoritative)

- Backtest 11.6y (2014-09 → 2026-04, 2114 bars 2D) : CAGR **+80.6%** · Sharpe **1.90** · MaxDD -28.2% · 41 trades · 75% win rate
- Buy-and-hold BTC same period : CAGR +56.1%, Sharpe 1.00, MaxDD -83.1% (the **MaxDD reduction** is the value proposition, not raw CAGR)
- OOS (2022-10 → 2026-04, 30%) : Sharpe 1.52
- MC 200 seeds ±1 bar : Sharpe IC95 [1.77, 2.01], P(Sharpe > 1.5) = 100%
- DSR Bailey-de Prado 2014 : 1.0000
- Live expected (Harvey-Liu 2015 + multi-régime, discount 0.75) : Sharpe **1.10-1.40**, CAGR **55-58%**

## Value proposition

Reduce BTC maximum drawdown from **-83% (buy-and-hold)** to **-28% (Hadès in-sample)**. We do not claim Hadès beats buy-and-hold on raw CAGR. Hadès is for investors who cannot or will not tolerate -80% drawdowns.

## Review rule

`review = max(2026-10-15, n_trades_closed_live ≥ 10)` — first GO/NO-GO capital deployment decision requires 6 months calendar AND ≥10 closed trades (statistical power requirement, DSR Bailey-de Prado).

## Disclaimer

Educational analytics tool. **Not investment advice.** Past performance does not guarantee future results. Forward paper test means no client capital is deployed; the strategy tracks real market data with frozen parameters for transparency and academic rigor. Cryptocurrency markets are highly volatile and can result in total loss. Consult a licensed financial advisor before any investment decision.

---

## Snapshots index

Each row = one cron run. SHA256 hashes of all frozen strategy files recorded in `*_integrity.json`.

| Date | Git commit | Sharpe (lifetime) | CAGR | MaxDD | 30d | 90d | 180d | 365d | Integrity |
|------|------------|-------------------|------|-------|-----|-----|------|------|-----------|
| 2026-04-18 | `cd901da` | 1.90 | 80.6% | -28.2% | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2026-04-19 | `4a43f0d` | 1.90 | 80.6% | -28.2% | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2026-04-20 | `54d5382` | 1.90 | 80.6% | -28.2% | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2026-04-22 | `696522a` | 1.90 | 80.6% | -28.2% | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2026-04-24 | `f415594` | 1.90 | 80.9% | -28.2% | ✅ | ✅ | ✅ | ✅ | ✅ |
| 2026-04-26 | `43e807e` | 1.90 | 80.9% | -28.2% | ✅ | ✅ | ✅ | ✅ | ✅ |
