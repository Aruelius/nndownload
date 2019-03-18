# nndownload
nndownload allows you to download videos from [Niconico](http://nicovideo.jp), formerly known as Nico Nico Douga. It simulates the HTML5 player by performing a session request to get the HQ source. Where not available, it will fallback to the Flash player. Keep in mind that if your account doesn't have premium, it may download the LQ source during economy mode hours (12 PM - 2 AM JST).
# nndownload
nndownload允许您从[Niconico](http://nicovideo.jp)下载视频，以前称为Nico Nico Douga。 它通过执行会话请求来模拟HTML5播放器以获取高清视频源。 如果没有，它将回退到Flash播放器。 请注意，如果您的帐户没开会员，则可以在N站的经济模式时段（12 PM  -  2 AM JST）下载低画质源。

## 功能
 - 下载包含评论，缩略图和元数据的视频
 - 下载Mylist
 - 为官方Niconama广播构建RTMP流URLs
 - 下载文本文件里的URLs

## 要求
### Python 版本
- Python 3.x

### 依赖包
- beautifulsoup4
- requests

## 使用说明
```
usage: nndownload.py [options] input

positional arguments:
  input                 URL or file # 视频链接地址

optional arguments:
  -h, --help            显示帮助
  -u USERNAME, --username USERNAME
                        用户名
  -p PASSWORD, --password PASSWORD
                        密码
  -n, --netrc           使用.netrc文件认证
  -q, --quiet           不输出日志
  -l, --log             把log输出到文件
  -v, --version         显示程序版本

download options:
  -y PROXY, --proxy PROXY
                        http or socks proxy
  -o OUTPUT_PATH, --output-path OUTPUT_PATH
                        自定义输出路径（参见模板选项）
  -f, --force-high-quality
                        只下载高清视频 # 开会员，或者在经济时间段下载
  -m, --dump-metadata   将视频元数据转储到文件
  -t, --download-thumbnail
                        下载视频缩略图
  -c, --download-comments
                        下载视频屏幕
  -e, --english         下载英语评论
```

Custom filepaths are constructed like standard Python template strings, e.g. `{uploader} - {title}.{ext}`. The available options are:

- comment_count
- description
- duration
- ext
- id
- mylist_count
- published
- size_high
- size_low
- thread_id
- thumbnail_url
- title
- uploader
- uploader_id
- url
- view_count

## 许可
This project is licensed under the MIT License.
