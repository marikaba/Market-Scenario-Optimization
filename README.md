# Market-Scenario-Optimization
This repository is part of the implementation of the article "A Comprehensive Framework for Market Scenario Prediction and Trading Strategy Simulation: Integrating Machine Learning with Optimized Technical Indicators Across S&amp;P 500 Sectors" by Maryam Bastani and Hossein Mohseni. It focuses on market scenario classification using technical indicators.
Market Scenario Classification Framework

The proposed market scenario classification framework provides a systematic approach to identify and classify market conditions based on technical indicators. It involves three key stages: calculating technical indicators, scoring them based on trend conditions, and classifying scenarios using threshold-based rules. By optimizing the weights assigned to each indicator and defining thresholds for scenario classification, the framework adapts to varying market dynamics. The classification outputs include labels such as "Strong Bullish," "Strong Bearish," "Oversold," "Overbought," and "Mixed Signals," which represent the prevailing market condition for a given data point.


---

Calculation of Technical Indicators for Market Scenario Classification

To facilitate market scenario classification, the framework calculates a set of widely used technical indicators using historical price data. These indicators include:

Simple Moving Average (SMA) and Exponential Moving Average (EMA) to identify price trends.

Moving Average Convergence Divergence (MACD) and its signal line to gauge momentum changes.

Relative Strength Index (RSI) to measure overbought or oversold conditions.

Bollinger Bands (BBANDS) to identify price deviations from the mean.

Stochastic Oscillator (%K and %D) for detecting potential reversals.

Average Directional Index (ADX) and directional indicators (DI+ and DI-) to evaluate trend strength.


These indicators serve as the foundation for assessing bullish and bearish tendencies within the data, enabling the formulation of a comprehensive market condition classification system.

---

Technical Indicators Scoring Mechanism and the Role of Weighting

The scoring mechanism translates the calculated technical indicators into numeric representations of market trends. For each data point, Bullish and Bearish Scores are computed by evaluating the conditions associated with upward and downward trends, respectively. Each condition is assigned a weight, reflecting its relative importance in predicting market behavior.

The weights are applied as follows:

Bullish conditions (e.g., SMA > EMA, MACD > Signal Line) and bearish conditions (e.g., SMA < EMA, MACD < Signal Line) contribute to their respective scores based on their assigned weights.

Additional conditions such as RSI within a neutral range, price position relative to Bollinger Bands, and Stochastic Oscillator values are also considered.


Bayesian optimization is used to fine-tune these weights within a continuous range (0 to 2). This ensures the scoring mechanism aligns with historical data patterns, thereby improving its classification accuracy.


---

Linking Scoring Mechanism to Scenario Classification: Thresholds Definition

The transition from scoring to classification involves the application of optimized thresholds. Two key thresholds, strong_thresh and over_thresh, are defined to categorize market scenarios:

If the Bullish Score exceeds strong_thresh, the scenario is classified as "Strong Bullish."

If the Bearish Score exceeds strong_thresh, the scenario is "Strong Bearish."

Intermediate scores relative to over_thresh indicate "Overbought" or "Oversold" conditions, while scores below both thresholds result in a "Mixed Signals" classification.


Bayesian optimization is employed to determine the optimal threshold values, ensuring they effectively distinguish between the various market scenarios. This step establishes a direct connection between the scoring mechanism and scenario labels, creating a robust and adaptive classification framework.
