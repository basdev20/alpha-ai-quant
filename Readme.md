# AlphaAIQuant: AI-Driven Market Insights and Alerts
   
This repository contains a comprehensive Python application designed for stock market analysis, sentiment analysis, and automated alerting through Slack. It integrates various APIs including Yahoo Finance for stock data, Bing Search for market news, Slack for notifications, and Azure OpenAI for sentiment analysis and prediction. The application is structured to perform technical analysis, sentiment analysis, and machine learning predictions to inform stock trading decisions.  
   
## Features  

![RAG Architecture](docs/OAI_2024.png)
   
- **Stock Data Fetching**: Downloads historical stock data from Yahoo Finance.  
- **Technical Analysis**: Calculates technical indicators such as Moving Averages, RSI, and MACD.  
- **Sentiment Analysis**: Fetches recent news articles related to specified stocks and analyzes their sentiment.  
- **Machine Learning Predictions**: Utilizes a RandomForestClassifier to predict stock price movements based on technical indicators.  
- **Slack Integration**: Sends automated alerts and analysis reports to a specified Slack channel.  
- **Azure OpenAI Integration**: Leverages Azure OpenAI for advanced sentiment analysis and stock movement predictions.  
- **Scheduling**: Runs analysis and alerting tasks at specified intervals, including market hours consideration.  
   
## Getting Started  
   
### Prerequisites  
   
- Python 3.9+  
- Slack Workspace and Bot Token  
- Bing Search API Subscription  
- Azure OpenAI Subscription  
   
### Installation  
   
1. Clone the repository:  
   
```bash  
git clone https://github.com/basdev20/alpha-ai-quant.git  
cd alpha-ai-quant 
```  
   
2. Install required Python packages:  
   
```bash  
pip install -r requirements.txt  
```  
   
3. Create a `.env` file in the root directory and populate it with your API keys and tokens:  
   
```plaintext  
SLACK_BOT_TOKEN=xoxb-your-slack-bot-token  
SLACK_CHANNEL=your-slack-channel-id  
BING_SUBSCRIPTION_KEY=your-bing-subscription-key  
AZURE_OPENAI_API_KEY=your-azure-openai-api-key  
AZURE_OPENAI_ENDPOINT=https://your-azure-openai-endpoint  
AZURE_OPENAI_DEPLOYMENT=your-azure-openai-deployment  
```  
   
4. Add `.env` to your `.gitignore` file to ensure your secrets are not checked into version control.  
   
## Usage  
     
The stock analysis and alert system is designed to provide flexibility in operation, catering to both real-time market analysis during trading hours and after-hours research or testing. Here's how to run the system in both scenarios:  
  
### During Market Hours  
  
To run the system in alignment with the stock market's trading hours, ensuring that analysis and alerts are generated based on live data, simply execute the main script without any additional flags:  
  
```bash  
python quant.py  
```

This command runs the system under its default configuration, which is optimized for live market conditions.

### After Market Hours
 
For conducting analysis or testing outside of standard trading hours, you can bypass the market hours check by using the --ignore-market-hours flag. This allows the system to operate as if the market were open, enabling after-hours data processing and analysis:

```bash 
python main.py --ignore-market-hours  
 ```
This flexibility ensures that the system can be utilized for a wide range of purposes, including but not limited to, after-hours trading strategy development, historical data analysis, and system testing.
Use the `--ignore-market-hours` flag to run the script outside of the standard market hours for testing purposes.  

![RAG Architecture](docs/T.png)


![RAG Architecture](docs/output.png)



### Configuration  
   
- **Slack Configuration**: Set your Slack Bot Token and Channel ID in the `.env` file.  
- **API Keys**: Provide your Bing Search API and Azure OpenAI API keys in the `.env` file.  
- **Stock Tickers**: Modify the `tickers` list in the script to include the stock symbols you want to analyze.  
   
## Contributing  
   
Contributions are welcome! Please feel free to submit pull requests, report bugs, and suggest features.  
   
## License  
   
Distributed under the MIT License. See `LICENSE` for more information.  
   
## Acknowledgments  
   
- Yahoo Finance for providing stock data.  
- Bing Search API for market news.  
- Slack for communication platform.  
- Azure OpenAI for cutting-edge AI models.  
   
## Disclaimer  
  
> :warning: **Important Notice**: This project, including all code, data, and information contained within it, is provided for educational and informational purposes only. It is not intended for actual trading or investment purposes. The creators and contributors of this project do not offer financial advice, endorse any specific trading or investment strategies, or guarantee the accuracy, completeness, or timeliness of any information or data provided.  
  
> :warning: **Risk Acknowledgment**: Trading stocks, securities, and other financial instruments involves substantial risk of loss and is not suitable for every investor. The valuation of stocks and securities may fluctuate, and as a result, investors may lose more than their original investment. The use of machine learning, technical analysis, or any other method within this project does not eliminate the inherent risks of trading.  
  
> :warning: **No Professional Advice**: The information provided in this project does not constitute investment advice, financial advice, trading advice, or any other sort of advice, and you should not treat any of the project's content as such. The project creators and contributors are not registered financial advisors and do not offer any personalized financial advice. Before making any financial decisions, you should consult with a qualified professional and conduct your own due diligence.  
  
> :warning: **Liability**: The creators and contributors of this project will not be held liable for any losses or damages resulting from the use of this project, including but not limited to trading or investment decisions based on the use of this project's code, data, or information.  
  
By using this project, you acknowledge and agree to the terms of this disclaimer. If you do not agree with them, you should not use this project.  


## Educational Notes on Key Components  
  
Our stock analysis and alert system utilizes several key financial indicators and analytical techniques to assess stock performance and market sentiment. Here's a brief overview of these components:  
  
### Technical Indicators  
  
- **RSI (Relative Strength Index)**: The RSI is a momentum oscillator that measures the speed and change of price movements. It oscillates between 0 and 100 and is typically used to identify overbought or oversold conditions in a stock. [Learn more about RSI](https://www.investopedia.com/terms/r/rsi.asp).  
  
- **MACD (Moving Average Convergence Divergence)**: The MACD is a trend-following momentum indicator that shows the relationship between two moving averages of a stock's price. It is used to identify bullish or bearish momentum. [Learn more about MACD](https://www.investopedia.com/terms/m/macd.asp).  
  
- **20-Day Moving Average**: This short-term moving average helps smooth out price data to identify the trend direction. It's often used in conjunction with the 50-Day Moving Average to determine crossover points indicative of potential market shifts. [Learn more about Moving Averages](https://www.investopedia.com/terms/m/movingaverage.asp).  
  
- **50-Day Moving Average**: This medium-term moving average is used to gauge the overall trend direction over a longer period. When it crosses above the 20-Day Moving Average, it may signal a bullish trend, and vice versa.  
  
### Sentiment Analysis  
  
Sentiment Analysis involves evaluating the sentiment or tone of text data to determine the overall opinion expressed within it. In the context of stock market analysis, it's used to assess the sentiment of news articles, social media posts, and other textual content related to a stock or the market in general. This can provide insights into public perception and potential market movements. [Learn more about Sentiment Analysis](https://www.investopedia.com/terms/s/sentimentanalysis.asp).  
  
### Machine Learning in Stock Prediction  
  
Our system employs machine learning models to predict stock price movements based on historical data and the calculated technical indicators. By analyzing patterns in the data, the model can make informed predictions about future price movements, aiding in decision-making processes.  
  
---  
  
By integrating these analytical techniques and indicators, our system provides comprehensive insights into stock performance, helping users make informed trading decisions.  

---  
   
By contributing to this project, you agree to adhere to its Code of Conduct and make a positive impact on the community. Let's build something great together!
