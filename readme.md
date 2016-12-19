#爬虫及文本分析实现

文档说明：

1.  news_spider.py是我自己写的一个很简单的单线程爬虫，可以直接用来爬取中国教育信息化网站上的新闻报道。


    网站对爬虫十分友好，甚至不用伪装成浏览器即可访问，代理IP什么的就更用不到了，是爬虫新手练习的好地方。不过，抓取量比较大的话，还是建议分批次抓取，设置好延迟时间，不要在短时间内猛爬，不然会给网站的服务器带去压力。
   
    我没有使用现有的爬虫框架；由于数据量不算大，我也没有给出重试机制的代码，写一个简单的循环即可实现。
  
2.  爬取中国知网的论文信息前，需要先获得相关论文的url队列，知网搜索后，论文的链接在静态页面中是看不到的;可以自己写代码解析js的返回值，以获取url；但知网对爬虫并不友好，很可能面临验证码输入(robot-check)甚至封锁IP的问题。

    我使用了专门的爬虫工具批量获取相关的论文链接，弹出验证码的检验框时，需手工输入。
 
    详情可参考集搜客的相关教程 -- http://www.gooseeker.com/ <br>
   
    获取了url队列后，即可直接批量解析页面内容，爬取并保存需要的信息。由于硕士、博士学位论文及期刊论文的页面排版略有差异，所以写了三份代码分别实现。代码见：cnki_xxx.py。

3. 文本挖掘和分析的代码我需要再整理一下，稍后上传。



最后的说明：我是python的初学者和爱好者，共同学习，欢迎交流。邮箱地址:betterus@126.com