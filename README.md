
# Gamma Indicator Strategy using VectorBTpro

This script implements a custom options market sentiment strategy using Gamma Exposure (GEX) data. It leverages VectorBTpro to generate signals, backtest, and visualize the performance.

## 💡 Strategy Logic

The script uses two key market behavior patterns:

1. **Reversal Signal (Short Bias):**
   - Price moves up sharply.
   - Net GEX (dealer positioning) declines.
   - Indicates possible short gamma pressure (dealers selling into strength).

2. **Coiled Signal (Long Bias):**
   - Price remains flat (low volatility).
   - Absolute GEX rises (dealers increasing positioning).
   - Suggests a buildup for a move (coiling).

## 🧠 Requirements

- Python 3.8+
- pandas
- vectorbtpro
- Pickle file with required columns:
  - `Spot_Close`
  - `close_net_gex`
  - `close_abs_gex`

## 📂 File Structure

- `gamma_ind.py`: Main strategy code with signal logic, backtest, and visualization.
- `NetGEX_AbsGEX_EPS(SPY).pickle`: Input data file (must be present in the working directory).

## 🚀 How to Run

```bash
python gamma_ind.py
```

It will display a performance summary and plot the strategy on a chart, overlaying reversal signals on price.

## 📈 Output

- VectorBT portfolio stats
- Equity curve with trade entries/exits
- Overlay chart: Price vs Net GEX with reversal markers

## 🛠️ Customization

- Adjust signal thresholds like `price_move > 0.2` or `abs(price change) < 0.1` to fine-tune sensitivity.
- You can plug in your own data by editing the `get_db_data()` function.

---

This strategy is educational and should not be used for live trading without evaluation.
