Gmeek 一个博客框架，超轻量级个人博客模板，完全基于 Github Pages 、 Github Issues 和 Github Actions，可以称作 All in Github。不需要本地部署，从搭建到写作，只需要 18 秒，2 步搭建好博客，第 3 步就是写作。

安装
安装及其简单，但是也要认真看下面的步骤，一步一步来。

点击通过模板创建仓库，建议仓库名称为 XXX.github.io，其中 XXX 为你的 github 用户名。

在你创建好的仓库的设置 Settings 中 Pages->Build and deployment->Source 下面选择 Github Actions。

打开一篇 issue，开始写作，并且添加一个标签（只添加一个），保存 issue 后会自动创建博客内容，片刻后可通过 https://XXX.github.io 访问

配置文件
按照安装步骤成功搭建好后，就可以阅读下面的内容修改配置文件啦。
注意修改配置文件后一定要手动全局生成一次，不然会报错。

config.json 文件就是配置文件，在创建的仓库内可以找到，默认填写的是我的信息，对应修改为自己的即可。

{
    "title":"Meekdai",
    "displayTitle":"eekdai",
    "subTitle":"童话是一种生活态度，仅此而已。",
    "homeUrl":"http://blog.meekdai.com",
    "avatarUrl":"http://meekdai.com/avatar.jpg",
    "faviconUrl":"http://meekdai.com/favicon.ico",
    "singlePage":[],
    "GMEEK_VERSION":"last"
}
以上是必须的字段，下面是可以自定义字段的描述，可以选择加入到 config.json 中。

"email":"meekdai@163.com",
"startSite":"02/16/2015",
"filingNum":"浙ICP备20023628号",
"onePageListNum":15,
"commentLabelColor":"#006b75",
"yearColorList":["#bc4c00", "#0969da", "#1f883d", "#A333D0"],
"i18n":"CN",
"dayTheme":"light",
"nightTheme":"dark_colorblind",
"urlMode":"pinyin",
"style":"",
"script":"",
另有不清楚的也可以参考 https://github.com/Meekdai/meekdai.github.io/blob/main/config.json

常见问题
搭建不成功
多半是没有按照安装步骤来，其实搭建就这 2 步，不要自己乱点乱设置，就不会有问题。
案例一：Meekdai/Gmeek#14
案例二：Meekdai/Gmeek#18
案例二：Meekdai/Gmeek#20

Actions 执行失败
修改了 config.json 配置文件后，需要全局生成。另外 label 标签没有打，或者多打也会出现这个问题。
建议通过 Actions->build Gmeek->Run workflow-> 里面的按钮全局重新生成一次
案例一：Meekdai/Gmeek#1
案例二：Meekdai/Gmeek#10

如果要导入以前的文章，如何设置发布时间呢？
如需修改发布时间，可以在文章最后一行添加如下代码。里面的时间是采用时间戳的形式，可以用如下网站转换。

<!-- ##{"timestamp":1490764800}## -->
自定义单篇文章页面的 style 和 script
<!-- ##{"style":"<style>#postBody{font-size:20px}</style>"}## -->
<!-- ##{"script":"<script async src='//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js'></script>"}## -->
可同时一起添加多种自定义参数：
<!-- ##{"script":"<script async src='//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js'></script>","style":"<style>#postBody{font-size:20px}</style>","timestamp":1490764800}## -->
添加全局文章页面的 style 和 script
在 config.json 文件中添加

"style":"<style>#postBody{font-size:20px}</style>",
"script":"<script async src='//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js'></script>",
置顶博客文章，只需要 Pin issue 即可。

如果在评论里面登录后评论报错，可直接按照提示安装 utteranc app 即可

Error: utterances is not installed on xxx/xxx.github.io. If you own this repo, install the app. Read more about this change in the PR.

如何魔改
如果有朋友想修改博客的主题，或者添加一些东西，这个框架是支持魔改的。所有的 UI 都在 templates 文件中，可进行修改，如果合适，我会合并到主线，通过配置文件让用户选择哪个主题。