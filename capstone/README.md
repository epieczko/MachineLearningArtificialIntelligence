### AI-Driven Sentiment Analysis to Enhance Stock Price Predictions

**Author**: Erik Pieczkowski

#### Executive Summary
This project examines whether AI-driven sentiment analysis, retrieved from EODHD, can enhance the prediction of stock price movements. By integrating financial news sentiment data into machine learning models, we aim to assess whether the inclusion of sentiment data improves the accuracy of stock price predictions, thus enhancing investment decision-making for portfolio managers.


#### Rationale
Financial news and market sentiment can have a profound effect on stock price movements. Portfolio managers often rely on traditional financial metrics to make investment decisions. By incorporating real-time news sentiment, we aim to determine if predictive models for stock prices can be improved, potentially giving investors a competitive edge in reacting to market changes.


#### Research Question
How can AI-driven sentiment analysis of financial news enhance the prediction of stock price movements?


#### Data Sources
- **Financial News Sentiment Data**: Retrieved from EODHD, which provides sentiment scores based on financial news articles.
- **Market Performance Data**: Historical stock prices and financial metrics sourced from Yahoo Finance and financial databases.

#### Methodology
1. **Data Collection**:
    - **Stock Price Data**: Historical stock price data is retrieved from Yahoo Finance, focusing on daily closing prices of S&P 500 stocks.
    - **Sentiment Data**: News sentiment scores are sourced from EODHD, which provides positive, neutral, and negative sentiment scores for financial news articles.

2. **Data Preprocessing**:
    - **Stationarity**: To ensure the stock price data is suitable for time series modeling, it is transformed into a stationary format. This involves differencing the data to remove trends and stabilize the mean over time, which is essential for models like ARIMA and SARIMAX.
    - **Feature Engineering**: The sentiment scores from EODHD are merged with the stock price data based on dates, allowing the integration of news sentiment with market performance data.

3. **Modeling**:
    - **Time Series Models**: Various models, including ARIMA, SARIMAX, Prophet, and LSTM, are trained on the historical stock data.
    - **Sentiment Integration**: News sentiment scores are added to the models to evaluate whether the inclusion of sentiment improves the prediction of stock price movements.

4. **Evaluation**:
    - Each model is evaluated based on performance metrics such as Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) to determine the accuracy of stock price predictions with and without the sentiment data.

#### Results
Initial findings suggest that incorporating news sentiment data improves the accuracy of stock price predictions. The LSTM model showed significant improvements in prediction accuracy when sentiment data was included, highlighting the potential of sentiment analysis to enhance traditional forecasting models.

#### Next Steps
1. **Expand to Other Tickers**: Apply the sentiment analysis and stock prediction models to tickers beyond SPY, broadening the scope of the analysis to test its generalizability across different sectors and companies.
2. **Create Custom Sentiment Scores**: Implement VADER sentiment analysis to generate custom sentiment scores from financial news and social media data. This will allow us to compare and potentially improve upon the sentiment scores provided by EODHD.
3. **Explore Sector-Based Price Drivers**: Further investigate how various factors, such as earnings, macroeconomic indicators, and sentiment, drive stock price movements in the S&P 500. Analyze how these drivers vary across different sectors, providing deeper insights into sector-specific investment strategies.
4. **Incorporate Macroeconomic Indicators**: Use data from FRED (e.g., interest rates, GDP growth, unemployment rates) to explore how macroeconomic factors influence stock price movements in the S&P 500. Analyze how these indicators impact different sectors and enhance the predictive models by integrating these economic variables.


#### Outline of project

- [Historical Stock Data](notebooks/Historical_Stock_Data.ipynb)
- [Historical News Data](notebooks/Historical_News_Data.ipynb)
- [Combine Valuations and Sentiment Data](notebooks/Combine_Valuations_Sentiment_Data.ipynb)
- [Train Stock Preduction Models](notebooks/Train_Stock_Prediction_Models.ipynb)


##### Contact and Further Information

For any questions or further information regarding this project, please feel free to reach out to:

- **Name**: Erik Pieczkowski
- **Email**: Erik.pieczkowski@gmail.com