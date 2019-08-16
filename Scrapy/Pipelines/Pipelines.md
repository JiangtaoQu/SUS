# Pipelines

- `open_spider()`——打开时调用此方法,只一次，类似于 init 。

![1563680452062](Pipelines.assets/1563680452062.png)

- `close_spider()`——和 open_spider 对应，关闭时调用此方法。一般用于关闭数据库

![1565579102794](Pipelines.assets/1565579102794.png)

## 导出 csv,json,xml

```bash
scrapy crawl project_name -o name.csv

scrapy crawl project_name -o name.json

scrapy crawl project_name -o name.xml

# 远程
scrapy crawl project_name -o ftp://user:pass@ftp.example.com/path/name.csv
```

