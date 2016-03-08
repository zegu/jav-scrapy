#jav-scrapy

一个可以爬取 AV 磁力链接或影片封面的小爬虫。

**仓库迁至 [github](https://github.com/raawaa/jav-scrapy)，此处不再更新。**

![anim.gif](https://ooo.0o0.ooo/2015/10/31/56345cf140299.gif "anim.gif")

## Prequisites

- Node.js 4.2.1+

## Installation

```bash
$ git clone https://git.coding.net/raawaa/jav-scrapy.git
$ cd jav-scrapy
$ npm install # 安装npm包依赖
$ npm link    # 使jav-scrapy全局可执行
```

## Usage

```bash
  Usage: jav [options]

  Options:

    -h, --help                output usage information
    -V, --version             output the version number
    -p, --parallel <num>      设置抓取并发连接数，默认值：2
    -t, --timeout <num>       自定义连接超时时间(毫秒)。默认值：30000毫秒
    -l, --limit <num>         设置抓取影片的数量上限，0为抓取全部影片。默认值：0
    -o, --output <file_path>  设置磁链和封面抓取结果的保存位置，默认为当前用户的主目录下的 magnets 文件夹
    -s, --search <string>     搜索关键词，可只抓取搜索结果的磁链或封面
    -b, --base <url>          自定义抓取的起始页
    -x, --proxy <url>         设置代理，例：-x http://127.0.0.1:8087
```

### Examples

```bash
# 抓取所有影片封面和磁链到 /path/to/covers/ 目录下，影片的封面和磁链归入以番号
# 命名的子文件夹中，并行下载数为 10
$ jav -o /path/to/folder -p 10         

# 抓取番号以 ipz 开头的所有影片，并保存在 /path/to/magnets.txt 中，并行抓取数 20
$ jav -s ipz -p 20 -o /path/to/folder

# 抓取番号为 ipz-634 的影片
$ jav -s ipz-634 -o /path/to/folder

# 抓取「连裤袜」主题的所有影片
$ jav -b http://www.javbus.in/genre/28

# 使用代理
$ jav -x http://127.0.0.1:8087
```

## Notes

- Windows 用户注目，如在 jav-scrapy 目录下直接运行 `jav` 命令可能会报错，可参考 [issue #1](https://github.com/raawaa/jav-scrapy/issues/1) 。
- 若影片存在高清资源，则优先抓取高清磁链。

## Contributors

- [@qiusli](https://github.com/qiusli)
- [@Eddie104](https://github.com/Eddie104)
