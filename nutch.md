# Crawling, indexing and searching with Nutch and Solr


http://www.lsi.upc.edu/~caim/lab/session4.html


```
export JAVA_HOME=$(readlink -f /usr/bin/java | sed "s:bin/java::")
export PATH=$PATH:$JAVA_HOME/bin
export classpath=.:$JAVA_HOME/lib

export NUTCH_RUNTIME_HOME=/home/sang/apache-nutch-1.9
export PATH=/home/sang/apache-nutch-1.9/bin:$PATH
```

for mac

export HADOOP_OPTS="-Djava.security.krb5.realm=OX.AC.UK -Djava.security.krb5.kdc=kdc0.ox.ac.uk:kdc1.ox.ac.uk"



http://blog.csdn.net/bitterliquor/article/details/40735903
http://my.oschina.net/xiaoen/blog/344089


执行抓取命令bin/crawl,命令格式为

Usage: bin/crawl <seedDir> <crawlDir> <solrURL> <numberOfRounds>

这里是: bin/crawl urls/ TestCrawl/ http://localhost:8080/solr/ 2



bin/crawl urls/ crawldb/ http://localhost:8983/solr/collection1 1



## hadoop single machine 
http://wiki.apache.org/nutch/NutchHadoopTutorial#Deploy_Nutch_to_Single_Machine


## re-crawl

http://pascaldimassimo.com/2010/06/11/how-to-re-crawl-with-nutch/


http://wiki.apache.org/nutch/bin/nutch_inject


## 流程

http://www.cnblogs.com/huligong1234/p/3515214.html


总结如下： 
1) 建立初始 URL 集 
2) 将 URL 集注入 crawldb 数据库---inject 
3) 根据 crawldb 数据库创建抓取列表---generate 
4) 执行抓取，获取网页信息---fetch

5) 解析抓取的内容---parse segment  
6) 更新数据库，把获取到的页面信息存入数据库中---updatedb 
7) 重复进行 3～5 的步骤，直到预先设定的抓取深度。---这个循环过程被称为“产生/抓取/更新”循环 
8) 根据 sengments 的内容更新 linkdb 数据库---invertlinks 
9) 建立索引---index



Nutch的数据文件: 

crawldb: 爬行数据库，用来存储所要爬行的网址。 
linkdb: 链接数据库，用来存储每个网址的链接地址，包括源地址和链接地址。 
segments: 抓取的网址被作为一个单元，而一个segment就是一个单元。
## 读取

➜  apache-nutch-1.9 git:(master) ✗ open .
➜  apache-nutch-1.9 git:(master) ✗ bin/nutch readdb crawldb/crawldb -stats 
CrawlDb statistics start: crawldb/crawldb
2014-12-09 19:41:55.778 java[20209:1003] Unable to load realm info from SCDynamicStore
Statistics for CrawlDb: crawldb/crawldb
TOTAL urls:	2921
retry 0:	2921
min score:	0.0
avg score:	8.589524E-4
max score:	1.476
status 1 (db_unfetched):	2861
status 2 (db_fetched):	59
status 7 (db_duplicate):	1
CrawlDb statistics: done



根据url读取

➜  apache-nutch-1.9 git:(master) ✗ bin/nutch  readdb crawldb/crawldb/ -url http://nutch.apache.org/
2014-12-09 19:43:36.122 java[20355:1003] Unable to load realm info from SCDynamicStore
URL: http://nutch.apache.org/
Version: 7
Status: 2 (db_fetched)
Fetch time: Thu Jan 08 18:38:42 CST 2015
Modified time: Thu Jan 01 08:00:00 CST 1970
Retries since fetch: 0
Retry interval: 2592000 seconds (30 days)
Score: 1.4761904
Signature: 2c1eb8ec14d238c24c2e92ade12860a8
Metadata: 
 	Content-Type=text/html
	_pst_=success(1), lastModified=0
	_rs_=1050
	
	
https://github.com/search?p=3&q=nutch+crawl&ref=searchresults&type=Code&utf8=%E2%9C%93

- https://github.com/L3S/nutch-injector

- https://github.com/chengpohi/nutch-web 差

- https://github.com/KINGgemeenten/websitecrawler/
- https://github.com/KINGgemeenten/websitecrawler/blob/master/scripts/local


bin/nutch org.apache.nutch.util.domain.DomainStatistics crawldb/crawldb/current/ host_stats host


- https://github.com/kmtaylor/nutch_scripts/blob/master/nutchbot.sh


bin/nutch readlinkdb crawldb/linkdb -dump dump

- https://github.com/cmpe297webcrawler/project


- https://github.com/rajskumar/semplest2/tree/master/SemplestCrawler/src/semplest/crawler
- https://github.com/rajskumar/semplest2/blob/master/SemplestCrawler/src/semplest/crawler/Run.java

bin/nutch readseg -dump crawldb/segments/$target_dir/ $crawl_dump_dir -nofetch -nogenerate -noparse -noparsedata -noparsetext



http://www.oschina.net/search?scope=project&q=nutch


http://git.oschina.net/dreamidea/neocrawler



https://github.com/wei-m-teh/nutch-web-api


## cankao 

- https://github.com/CrawlScript/WebCollector
- http://my.oschina.net/laiweiwei/blog/100866
- https://github.com/internetarchive/heritrix3


网络爬虫调研报告 http://zuoqiang.iteye.com/blog/1553026

http://edu.ibeifeng.com/view-video-id-293.html


https://github.com/shiftdirector/youseer



http://crawler.archive.org/articles/developer_manual/processor.html


http://code.google.com/p/gtxcontentconnector/wiki/HowTo_Nutch


http://www.cse.iitb.ac.in/~pb/papers/coling12-wssanlp-multilingual-index.pdf

## 基于Lucene4.6+Solr4.6+Heritrix1.14+S2SH实战开发从无到有垂直搜索引擎
如果需要就买下来

http://www.ibeifeng.com/goods-378.html