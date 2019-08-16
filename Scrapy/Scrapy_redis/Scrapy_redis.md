# Scrapy redis

![u=2727356281,1022137638&fm=11&gp=0](Scrapy_redis.assets/u=2727356281,1022137638&fm=11&gp=0.jpg)

- settings

```python
# Enables scheduling storing requests queue in redis.
SCHEDULER = "scrapy_redis.scheduler.Scheduler"

# Ensure all spiders share same duplicates filter through redis.
DUPEFILTER_CLASS = "scrapy_redis.dupefilter.RFPDupeFilter"

# Store scraped item in redis for post-processing.
ITEM_PIPELINES = {
    'scrapy_redis.pipelines.RedisPipeline': 300
}
```

- <strong>scrapy_redis/default.py</strong>

![1564125041146](Scrapy_redis.assets/1564125041146.png)

- <strong>scrapy_redis/scheduler.py</strong>

![1564122237035](Scrapy_redis.assets/1564122237035.png)

- <strong>scrapy_redis/dupefilter.py</strong>

![1564123857346](Scrapy_redis.assets/1564123857346.png)

![1564124171975](Scrapy_redis.assets/1564124171975.png)

![1564123554523](Scrapy_redis.assets/1564123554523.png)

- <strong>scrapy_redis/settings.py</strong>

![1564132501140](Scrapy_redis.assets/1564132501140.png)

- Terminal

1. run the spider:

   ```bash
   scrapy runspider 【spider.name】.py
   
   scrapy runspider gcbidding.py
   
   debug 也行
   ```

2. push urls to redis:

   ```bash
   redis-cli lpush 【spider.name】:start_urls http://google.com
   ```

```bash
redis-cli lpush gcbidding:start_urls https://www.gcbidding.com/portal/bidding
```



