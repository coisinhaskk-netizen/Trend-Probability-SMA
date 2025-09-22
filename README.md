📊 Trend Probability Indicator with Moving Average - MQL5

This project implements a custom indicator for MetaTrader 5 that analyzes the short-term trend of the DXY (US Dollar Index). It calculates an accumulated probability of bullish or bearish movement based on historical price comparison and plots a Simple Moving Average (SMA) of this probability on the chart.

🚀 Features

The indicator:

Compares the current price of DXY with its price 10 minutes ago.

Accumulates the trend direction statistics over time (bullish or bearish).

Stores these probabilities in an internal history.

Calculates a Simple Moving Average (SMA) of the probabilities.

Plots the SMA line on the chart in Deep Sky Blue (clrDeepSkyBlue).

⚙️ Input Parameters
input int MA_Period = 10;


MA_Period: Number of past probability values used to calculate the moving average. Higher values smooth the signal.

📈 Indicator Buffer

bufferSMA[]: Stores the SMA values for drawing the line on the chart.

🧠 Strategy Logic

The TrendFollow class implements the core logic:

Retrieves current and historical close prices of DXY at M1 timeframe:

iClose("DXY", PERIOD_M1, 0) vs. iClose("DXY", PERIOD_M1, 10)

Increments internal counters for bullish or bearish trends.

Calculates the accumulated trend probability based on this historical record.

This probability is smoothed using a Simple Moving Average (SMA) and plotted on the chart.

🖥️ How to Use

Copy and paste the code into a new .mq5 file inside your MQL5/Indicators/ directory.

Compile the file using MetaEditor.

Attach the indicator to any chart — the indicator will internally analyze the DXY symbol.

Observe the blue line for a smoothed view of recent trend probabilities.

⚠️ Make sure the DXY symbol is available and has sufficient historical data in your MetaTrader 5 platform.

🔍 Console Output Example

The indicator also prints real-time log messages like:

Trend: Bullish | Accumulated Probability: 73.33%
Trend: Bearish | Accumulated Probability: 66.67%
No price change.


These logs help you track how the algorithm is interpreting market trends.

📌 Notes

This indicator is experimental and can serve as the foundation for more advanced trend-following strategies.

It depends on external data (DXY), so ensure the asset is available and updated in your platform.

🛠️ Requirements

MetaTrader 5

DXY symbol available in Market Watch

Sufficient M1 historical data

📄 License

This code is free to use for educational and experimental purposes. Contributions and modifications are welcome.
