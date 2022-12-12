# 基于 Python 社交媒体数据分析的中国 a 股交易

> 原文：<https://blog.quantinsti.com/trading-china-share-stocks-based-social-media-data-analysis-python/>

In this article, we will understand how natural language processing, [sentiment analysis](https://blog.quantinsti.com/tag/sentiment-trading/) and social media play a role in the share markets with the help of [Python](https://blog.quantinsti.com/tag/python-for-trading/). This would be explained with respect to the trading in China markets A-share stocks.

This article is the final project submitted by the authors as a part of their coursework in the [Executive Programme in Algorithmic Trading](https://www.quantinsti.com/epat) (EPAT<sup>®</sup>) at QuantInsti<sup>®</sup>. Do check our [Projects page](https://blog.quantinsti.com/tag/epat-trading-projects/) and have a look at what our students are building.

## **关于作者**

The author of this blog is **Fan Zhang**, an Assistant Analyst at Fitch (Bohua) Rating located in Beijing, China. Fan is an Engineer, completing his Master of Financial Engineering from Cornell University.
                                                     ![text](img/f57bc0e0d9a07834a9f3cbc586c9b958.png)

## **动机**

I have been working as a day trader in China A-shares for 2.5 years and frequently check insights from experts on [Weibo](https://www.weibo.com) (Chinese version of [Twitter](https://twitter.com/)). Based on my experience, the general consensus from social media is predictive of China A-share stock performance in 2-3 days.

By attending the EPAT programme, I learned a comprehensive understanding of quantifying various trading strategies through intensive projects on real market data. Therefore, I am eager to utilize this final project to research my own trading strategy: **the forecasting power of social media for the stock market. **So, let’s proceed with the project.

## **数据集**

i) Stock data for China A-share equitiesDaily equity data includes the date, high, low, open, close, adjusted close and volume. This historical equity data ranges from January 2014 to July 2017.ii) Social media dataWeibo (the Chinese twitter) can be accessed through API, but the Weibo content retrieved and requesting frequency are limited for free accounts. For example, if one account requests more than ~5000 times in 30 minutes through API, the corresponding Weibo account will be blocked for further access.

## **入围 id**

Because of the API requesting limitation and the noise in thousands of not-so-informative public accounts, for this project, twenty Weibo financial IDs were selected based on trading experience.

A strong assumption is that these selected IDs are insightful market players and that the consensus inferred from their tweets will be predictive of future market movements.

The retrieved tweets starting date varies among different IDs. The backtest period is determined as 2016-10-01 to 2017-07-14.

## **策略**

*   在每个交易日上午 00:00-09:30 期间，从认可的微博理财 id 获取社交媒体数据。
*   选择四个有代表性的、被广泛交易或讨论的行业作为潜在的投资组合构成。
*   如果某个板块被至少 3 个专家看好(微博理财 id)，就买这个板块的龙头股。股票在投资组合中的资本权重相等。
*   开盘价买入，持有一天，第二天开盘价卖出。

## **扇区**

Sectors in consideration: Artificial Intelligence (AI), Banking, Lithium and Securities. These sectors were chosen because they are frequently discussed sectors and their corresponding keywords are easy to parse using Natural Language Processing techniques, thus avoiding ambiguities in analyzed tweets.

In each sector, only the most five representative and actively-traded equities are bought if the related sector is favoured by Weibo expert consensus.

## **中文自然语言解析器**

Although several Chinese natural language parsers are available, there is no one package is designed for the Chinese financial market. So many financial keywords are not correctly parsed.

For example, the equity “**Bank of China (****中国银行)**” will be parsed into “**China (中国)**” and “**Bank (银行)**”, instead of being recognized as a whole. Such wrong-parsings due to the lack of a financial keyword database create confusion for trading decisions.

Therefore, modifications were made to one public Chinese language parser ([HanLP](http://hanlp.com/)). Chinese financial dictionary was constructed for this project with 4952 financial keywords, including all traded A-share equities and most slangs/jargons used in Weibo tweets.

The modified Chinese financial parser significantly improved parsing performance for trading.

## **情感分析**

The [sentiment analysis trading](https://quantra.quantinsti.com/course/sentiment-analysis-in-trading) is performed through a commercial package: [BosonNLP](https://bosonnlp.com/). For each tweet, the sentiments will consist of two scores for positive tendency and negative tendency, respectively; the sum of the two scores will be 1.

For example, the sentiment scores for “This meal is good” are 0.98 and 0.02, which signifies that this statement is strongly positive and the two scores sum to 1.

## **战略绩效**

The criterion for a buy consensus is set as at least three Weibo IDs favour one sector on one particular day during 00:00-09:30 am.

There are 188 trading days between 2016-10-01 and 2017-07-14 in the Chinese A-share market. Four trading opportunities were traded: two for AI and two for Securities. Three out of these four trades yields positive PnL. 

你可以报名参加 Quantra 上的[情绪分析课程](https://quantra.quantinsti.com/course/sentiment-analysis-in-trading)，这将帮助你利用 Twitter、新闻情绪数据设计新的交易策略。在本课程中，你将学习通过量化市场情绪来预测市场趋势。

## **结论**

This strategy achieved a **3.74% return** (annualized return 5.14%) and a **Sharpe ratio of 0.86**. You can check out the complete project along with related files, python codes and examples in the download section below.

If you want to learn various aspects of Algorithmic trading then check out the [Executive Programme in Algorithmic Trading (EPAT<sup>®</sup>)](https://www.quantinsti.com/epat/). The course covers training modules like Statistics & Econometrics, Financial Computing & Technology, and Algorithmic & Quantitative Trading. EPAT equips you with the required skill sets to build a promising career in algorithmic trading. [Enroll now](https://www.quantinsti.com/epat/)!

<small>Disclaimer: The information in this project is true and complete to the best of our Student’s knowledge. All recommendations are made without guarantee on the part of the student or QuantInsti®. The student and QuantInsti® disclaim any liability in connection with the use of this information. All content provided in this project is for informational purposes only and we do not guarantee that by using the guidance you will derive a certain profit./overseas</small>

#### **下载中的文件列表:**

*   最终项目 PDF 文件
*   项目的 3 个 Python 代码文件