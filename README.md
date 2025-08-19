End-to-end QR workflow (features → ML models → walk-forward backtest).

## Quick Start
1) `python -m venv .venv && . .venv/bin/activate`
2) `pip install -U pip && pip install -r requirements.txt`
3) `python -m src.data.download_data --tickers-file data/tickers_sp100_sample.txt --out data/ohlcv.parquet`
4) `python -m src.features.features --ohlcv data/ohlcv.parquet --out data/features.parquet`
5) `python -m src.models.train_xgb --features data/features.parquet --out runs/xgb.json`
6) `python -m src.backtest.backtest --features data/features.parquet --signals runs/xgb_signals.parquet --out runs/backtest_xgb.parquet`
