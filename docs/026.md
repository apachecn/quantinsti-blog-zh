# 如何使用 Python 和 Twitter API v2 获取推文

> 原文：<https://blog.quantinsti.com/twitter-api-v2/>

由[乌迪莎·阿洛克](http://www.linkedin.com/in/udisha-alok)

在这篇博客中，我们继续使用 Tweepy 的 API 接口探索 Twitter API 的高级搜索功能，了解费率限制以及如何处理它们，并了解 Twitter 上的本地趋势。

我们还将了解 Tweepy 库为 Twitter API v2 提供的客户端接口，以及如何使用它从 Twitter 获取不同类型的数据。

在这个小系列的前一篇博客中，我们介绍了使用 [Twitter API v1](/python-twitter-api/) 接口从 Twitter 获取不同类型数据的方法。我们还研究了 Twitter API 的访问级别类型。

在这里，我们将讨论以下主题:

*   [高级搜索](#premium-search)
    [搜索最近 30 天](#search-last-30-days)
    [搜索完整存档](#search-the-full-archive)
*   [速率限制](#rate-limits)
    [如何查看速率限制状态？](#how-to-check-the-rate-limit-status)
    [如何设置 app 等待直到速率限制被补足？](#how-to-set-the-app-to-wait-till-the-rate-limit-is-replenished)
*   [获取一个位置的趋势](#get-trends-for-a-location)
*   【Twitter API v2 的 Tweepy 客户端
*   [客户端认证](#client-authentication)
*   [使用客户端](#get-the-user-name-for-a-particular-user-id-using-client)获取特定用户 ID 的用户名
*   [使用客户端](#get-the-user-id-for-a-particular-user-name-using-client)获取特定用户名的用户 ID
*   [使用客户端](#get-the-user-names-for-multiple-user-ids-using-client)获取多个用户 id 的用户名
*   [使用客户端](#get-tweet-s-with-tweet-id-s-using-client)获取带有推文 Id 的推文
*   [使用客户端获取用户的关注者](#get-a-user-s-followers-using-client)
*   [使用客户端](#get-users-that-the-user-follows-using-client)获取用户关注的用户
*   [使用客户端获取用户的推文](#get-a-user-s-tweets-using-client)
*   [使用客户端](#get-tweets-that-a-user-liked-using-client)获取用户喜欢的推文
*   [获取使用客户端转发推文的用户](#get-users-who-retweeted-a-tweet-using-client)
*   [使用客户端搜索最近的推文](#search-recent-tweets-using-client)
*   [使用客户端](#get-tweet-count-for-a-search-query-using-client)获取搜索查询的 tweet 计数
*   [客户端分页](#pagination-in-client)
*   [使用扩展获取用户和媒体信息](#using-expansions-to-get-user-and-media-information)
*   [将搜索结果写入文本文件](#writing-the-search-results-to-a-text-file)
*   [将搜索结果放入数据帧](#putting-the-search-results-into-a-dataframe)
*   [Twitter API v2 GitHub](#twitter-api-v2-github)

* * *

## 高级搜索

Premium search 是 Twitter 提供的订阅 API。该 API 提供了两种产品:

*   搜索推文:30 天终点
*   搜索 Tweets:完整存档端点

要开始使用任何订阅 API，您需要为端点设置一个开发环境 [⁽ ⁾](https://developer.twitter.com/en/account/environments) 。

* * *

### 搜索最近 30 天

Twitter 提供高级搜索 Tweets: 30 天 API，让你可以访问过去 30 天内发布的 Tweets。你可以搜索这个数据库，其中的推文与你的查询相匹配并被返回。

可以使用 API 类的 **search_30_day** ()方法来访问这个特性。