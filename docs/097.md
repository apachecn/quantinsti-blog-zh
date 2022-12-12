# 在巴西进行成对交易，在美国市场进行短期跨界交易[ALGO 交易项目]

> 原文：<https://blog.quantinsti.com/algo-trading-epat-projects-12-april-2022/>

## 完整记录

[https://www.youtube.com/embed/hmX22QSY2qk?rel=0](https://www.youtube.com/embed/hmX22QSY2qk?rel=0)

完整的演示幻灯片可以在下面找到。

* * *

## 关于演示文稿

本次会议有两位我们尊敬的 EPAT 校友的项目陈述。首先是巴西 Luiz Guedes 博士的“巴西股票市场的配对交易”；第二个是阿联酋西达尔特·巴蒂亚的“对 SPX 指数的空头回补检验”。

### 项目 1:巴西股票市场的配对交易

[https://www.slideshare.net/slideshow/embed_code/key/pCOVxrWH3YRW0J?hostedIn=slideshare&page=upload](https://www.slideshare.net/slideshow/embed_code/key/pCOVxrWH3YRW0J?hostedIn=slideshare&page=upload)

完整项目:[巴西股票市场的统计套利对交易](/statistical-arbitrage-pair-trading-brazil-stock-market-project-luiz-guedes/)

这个项目为巴西的 B3(前 Bovespa)证券交易所建立了一个统计套利对交易策略模型。我们在两个不同的时间间隔运行我们的策略。2009 年 1 月 1 日至 2014 年 12 月 31 日以及 2018 年 1 月 1 日至 2021 年 4 月 30 日。由于我们只有当前的部门分布可用，前一时期的结果明显遭受生存偏差。

股票板块分类是直接从巴西 B3 证券交易所下载的。在所有行业中，我们只考虑了拥有五只或更多股票的行业，即:石油、金属、钢铁、纸张、运输材料、机器、铁路、公路、仓储、服务、农业、肉类、食品、建筑、纺织品、服装、鞋、教育、汽车租赁、零售、医院、药店、信息技术、电信、电力、水、银行、金融服务、保险和房地产。

结果非常令人鼓舞，尽管没有考虑交易费用或滑点成本。所有计算都基于每日收盘价。

### 项目 SPX 指数短跨回测

[https://www.slideshare.net/slideshow/embed_code/key/7HHjq64BhIQnxo?hostedIn=slideshare&page=upload](https://www.slideshare.net/slideshow/embed_code/key/7HHjq64BhIQnxo?hostedIn=slideshare&page=upload)

有很多研究都在讨论机械地卖出股票指数的期权，比如 SPX，NIFTY，BANKNIFTY 等。由于持续的市场风险溢价被称为“差异风险溢价”，它被认为是长期盈利的。这是因为隐含波动率高于指数的实际已实现波动率。由于恐惧/不确定性，市场参与者为期权支付了过高的价格，因此指数期权通常定价过高。在正常的市场机制下，期限较长的期权定价高于短期期权。

这是一个简单的策略，在 SPY ETF 上每周机械地卖出 45-60 天的跨仓，每天做一次 delta 对冲。为避免疑问，多头是一种期权头寸，在这种情况下，一个人在货币买入时卖出，然后将期权放在一起，将净贷方记入账户。

当标的表现出的波动性低于卖出期权的初始定价时，它就起作用了。简而言之，当基础资产在启动时没有从选择的 ATM 攻击移动太远或太多时，它就起作用了。

利润大致是启动时隐含波动率和终止时已实现波动率之间的差额，乘以多空双方的 vega 敞口。

* * *

## 扬声器

### Luiz Guedes 博士(巴西奥卡姆定量分析主管)

<figure class="kg-card kg-image-card">![Dr Luiz Guedes pic](img/b8821df039b638f7b4e7aaf9416faa91.png)</figure>

Luiz Guedes 博士在软件开发领域拥有 30 多年的经验，尤其是在支付卡行业。此外，他还是 IME 军事学院的教员，教授编译器和编程语言。

作为一名软件开发人员和创新者，Guedes 博士广泛使用创新的问题解决方法为受限系统和安全电子交易编写软件，尤其是在编程和执行环境、加密算法和安全通信协议的开发方面。

2021 年 7 月，在完成 QuantInsti 的 EPAT 项目一个月后，他开始担任 Occam Brasil 的定量分析主管，他刚刚被邀请成为该公司的合伙人。

Guedes 博士拥有 PUC/里约热内卢天主教大学计算机科学博士学位、IME 计算机系统硕士学位和计算机工程师学位。此外，他还获得了 FGV getu lio Vargas 基金会的工商管理硕士学位。

### 西达尔特·巴蒂亚(阿联酋第三集团 FZ 有限责任公司执行董事)

<figure class="kg-card kg-image-card">![Siddharth Bhatia pic](img/817023c8b05f53e6af499a5002e6d4ac.png)</figure>

西达尔特自 2006 年以来一直在孟买工作，目前在迪拜工作，自 2011 年以来拥有具体的交易经验。他最初是一家活跃在美国和欧盟债券期货市场的阿联酋本地自营公司的交易员，拥有交易期货的经验。

然后，他转到一家著名的家族办公室从事交易，管理着一个活跃于全球指数和期货期权的波动性交易账户。然后，他在一家财富管理公司工作，为公司的客户监督结构化产品的定价和交易以及各种保护性/尾部风险策略。在这里，他还负责包含结构化产品和基金的复杂账簿的投资组合管理。

从 2018 年开始，他创立了一家名为 Third Group 的自营交易和投资研究公司。第三组活跃于波动性交易，应用先进的定量分析来开发和部署交易策略。

西达尔特是 CFA 特许会员，于 2012 年获得特许会员资格。他是 2021 年第 50 批毕业的 QuantInsti EPAT 项目校友。他对算法交易有浓厚的兴趣，主要是探索所有类型的机器学习和人工智能，以在市场中获得优势。

* * *

本次活动于:
*2022 年 4 月 12 日星期二
东部时间上午 9:30 | IST 时间晚上 7:00 |新加坡时间晚上 9:30*