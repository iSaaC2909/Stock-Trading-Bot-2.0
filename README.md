# StockTrading-2.0

## Overview
StockTrading-2.0 is a C++ stock trading simulation platform that allows users to create and simulate multiple trading bots with different strategies over historical stock data. The simulation fetches real stock data from Yahoo Finance and provides analytics and visualizations of bot performance.

## Features
- Simulate multiple trading bots with different strategies:
  - Conservative
  - Aggressive
  - Passive
- Fetch historical stock data from Yahoo Finance (via libcurl)
- Customizable simulation period, stock symbols, and trading intervals (daily, weekly, monthly)
- Portfolio analytics and trade export
- Visualization of portfolio performance using Gnuplot

## Directory Structure
```
Stocktradingbot/
├── main.cpp                # Entry point for the simulation
├── analytics.h/.cpp        # Analytics and visualization functions
├── gnuplot-iostream.h     # Gnuplot C++ interface (requires Boost)
├── bot/                    # Trading bot logic and strategies
├── stock/                  # Stock data models and Yahoo Finance API
├── temporal/               # Date/time utilities and interval logic
```

## Dependencies
- C++11 or later
- [Boost](https://www.boost.org/) (for gnuplot-iostream)
- [Gnuplot](http://www.gnuplot.info/) (for visualization)
- [libcurl](https://curl.se/libcurl/) (for Yahoo Finance API)

## Build Instructions
1. **Install dependencies:**
   - Boost libraries
   - Gnuplot
   - libcurl
2. **Compile:**
   - There is no provided Makefile or CMakeLists.txt. You can compile with a command like:
     ```sh
     g++ -std=c++11 -I. -I./bot -I./stock -I./temporal main.cpp analytics.cpp bot/Bot.cpp bot/Position.cpp bot/Trade.cpp stock/Stock.cpp stock/StockSimulation.cpp stock/StockSimulationBuilder.cpp stock/YahooFinanceAPI.cpp temporal/TemporalUtils.cpp temporal/TemporalIterator.cpp temporal/Interval.cpp -o stocktrading -lboost_iostreams -lboost_system -lcurl
     ```
   - Adjust include/library paths as needed for your system.

## Usage
1. **Run the simulator:**
   ```sh
   ./stocktrading
   ```
2. **Follow the prompts:**
   - Enter the number of bots and configure each bot (type, name, starting balance, deposit period/amount)
   - Enter the simulation start/end dates (YYYY-MM-DD)
   - Choose the interval (daily, weekly, monthly)
   - Enter the stock symbols to simulate (e.g., AAPL, TSLA)
3. **Simulation output:**
   - Portfolio performance and trades are displayed/exported
   - Analytics and visualizations are generated as PNG files

## Notes
- Ensure you have an active internet connection for Yahoo Finance data.
- The project is intended for educational and research purposes only.

## License
This project is provided as-is for educational use. See source files for any third-party license information. 