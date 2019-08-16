# Scrapy_redis_bloomfilter

`pip install scrapy_redis_bloomfilter `

- BloomFilter

BloomFilter 主要用于检索一个元素是否在集合中。优点是空间效率和查询效率比较高。缺点是存在误判率。

![20171228104419270](Scrapy_redis_bloomfilter.assets/20171228104419270.png)

- <strong>scrapy_redis_bloomfilter/default.py</strong>

![1564125051079](Scrapy_redis_bloomfilter.assets/1564125051079.png)

- <strong>scrapy_redis_bloomfilter/scheduler.py</strong>

![1564122383737](Scrapy_redis_bloomfilter.assets/1564122383737.png)

- <strong>scrapy_redis_bloomfilter/dupefilter.py</strong>

![1564124424449](Scrapy_redis_bloomfilter.assets/1564124424449.png)

![1564124524548](Scrapy_redis_bloomfilter.assets/1564124524548.png)

![1564124583658](Scrapy_redis_bloomfilter.assets/1564124583658.png)

- <strong>scrapy_redis_bloomfilter/settings.py</strong>

![1564132975312](Scrapy_redis_bloomfilter.assets/1564132975312.png)

## 只去重 detail_url 不去重 list_url

- <strong>scrapy_redis_bloomfilter/scheduler.py</strong>
- <strong>spiders</strong>——custom_setting：是对setting中的文件内容进行覆盖。

![1565757355405](Scrapy_redis_bloomfilter.assets/1565757355405.png)

> 由于 scheduler.close 没有传 Spider 所以取不到 list_url 的库名，但使用 custom_settings 对 SCHEDULER_DUPEFILTER_KEY 进行覆盖就可以获取到了。

![1564139362682](Scrapy_redis_bloomfilter.assets/1564139362682.png)

- <strong>scrapy_redis_bloomfilter/dupefilter.py</strong>

![1564139623447](Scrapy_redis_bloomfilter.assets/1564139623447.png)

## 慕课

```shell
# 需要 c++ buildtools 
pip install mmh3
```

<ul>
    <li><a href='py_bloomfilter.py
        '>py_bloomfilter</a></li>
</ul>

https://devblogs.microsoft.com/python/unable-to-find-vcvarsall-bat/

- <strong>dupefilter.py</strong>

![1564140827442](Scrapy_redis_bloomfilter.assets/1564140827442.png)

![1563695292482](Scrapy_redis_bloomfilter.assets/1563695292482.png)

![1563695192208](Scrapy_redis_bloomfilter.assets/1563695192208.png)

![1564145442651](Scrapy_redis_bloomfilter.assets/1564145442651.png)

- <strong>scheduler.py</strong>

![1564142225999](Scrapy_redis_bloomfilter.assets/1564142225999.png)

![1564145239569](Scrapy_redis_bloomfilter.assets/1564145239569.png)

- <strong>spider.py</strong>

![1564145298309](Scrapy_redis_bloomfilter.assets/1564145298309.png)

![1564145718772](Scrapy_redis_bloomfilter.assets/1564145718772.png)

![1564145691301](Scrapy_redis_bloomfilter.assets/1564145691301.png)

- <strong>settings.py</strong>

![1564145647293](Scrapy_redis_bloomfilter.assets/1564145647293.png)

