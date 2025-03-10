目录
- [V1.3开发升级预告](#v1.3)
- [V1.2开发升级预告](#v1.2)
- [V1.1升级日志](#v1.1)


采集内容，图片不正确

# 开发日志
## TODO
- [ ] a 标签中的英文括号统一转成中文括号
- [ ] 增加文档发布的审核开关功能，避免一些用户发布垃圾文档(所有公开发布的文档都必须先审核)
- [ ] 审核管理
    - [ ] 书籍点评审核管理
    - [ ] 书籍公开发布审核管理
- [ ] 文档采集，replace过滤和替换采集到的网页标签和内容，图片懒加载的文档项目，也无处可逃。
- [ ] 导出markdown
- [ ] 在线HTML转markdown工具
- [ ] 直接访问编辑页面，登录的cookie过去无法编辑文档问题
- [ ] 直接编辑文档的时候，跳转到指定的编辑文档
- [ ] 管理后台增加标签管理和搜索关键字管理
- [ ] 书籍发布队列
- [ ] 增加相关书籍推荐功能（开启了全文搜索才会生效）
- [ ] 增加广告管理功能
- [ ] 电子书下载页面，扩展站点页面
- [ ] 搜索结果页，显示书籍电子书下载功能
- [ ] 书籍导出markdown功能（只供发布人使用）
- [ ] 书籍导出静态HTML功能（只供发布人使用），以便用户搭建静态网站
- [ ] 电子书检验，不存在的电子书，重新生成
- [ ] `<bookstack-auto/>`功能，如果当前文档的内容为空，则获取下一级文档title进行内容填充
- [ ] ~~增加打赏按钮显示与隐藏（根据书籍而定，默认隐藏）~~
- [ ] 增加电子书下载管控，是否必须登录才能下载电子书
- [ ] 发布队列


<a name="v2.0"></a>
## V2.0 开发升级日志

- [x] 微信小程序API接口开发
- [x] 书籍在发布的时候，把非站内图片自动采集下来
- [x] `BookStack` 配套微信小程序 `BookChat` API接口实现，累计20+个API接口
- [x] 修复删除项目时误删默认封面的bug
- [x] HTML内容处理，以兼容微信小程序`rich-text`组件实现微信小程序文档内容渲染
- [x] 开源书籍和文档收录提交入口以及收录管理
- [x] 增加网站小程序码功能，打通PC端与移动端一体化阅读浏览
- [x] 内容采集增强和优化
- [x] 评论审核与管理功能开发
- [x] 微信小程序配置(在 `app.conf` 文件中)
- [x] 横幅管理
- [x] 支持 `epub` 导入
- [x] 隐藏附件管理入口(因为不依赖于此管理附件)
- [x] 管理后台可根据用户名、昵称、邮箱和角色对用户进行检索和管理
- [x] 增加`作者`角色，用于控制普通用户创建项目权限

## v1.7 升级日志
- [x] 增加书籍和文档搜索精度控制（在管理后台可设置）
- [x] 增加`钉子`功能，把想要置顶的书籍置顶在`发现`列表页首位
- [x] 文档阅读，移动端展开菜单优化(右下角增加展开菜单按钮)
- [x] 跳转编辑指定文档
- [x] 流程图、时序图、数学公式的支持和优化
- [x] 移除外部引入的js、css公共资源库，实现本地化和内网部署的优化
- [x] 文章`内容目录`显示优化
- [x] 管理员删除书籍,需要输入管理员密码
- [x] 增加书籍语种分类（中文、英文、其他）
- [x] 增加首页最新推荐书籍内容
- [x] 增加关联书籍推荐功能(需要启用elasticsearch)
- [x] SEO 优化，如果文档内容图片缺少`alt`，自动使用文档标题填充
- [x] 采集HTML的时候，block 里面的内容不转markdown
- [x] 书籍分类统计不正确的问题
- [x] 采集功能增强，自带截图功能。
- [x] 更新MySQL驱动，支持MySQL 8.x


## V1.6 升级日志


- [x] 使用`puppeteer`采集的支持（需要安装node以及在当前程序目录下安装node的puppeteer模块）
- [x] 根据邮箱找回密码
- [x] `<bookstack-split></bookstack-split>`，文档拆分功能
- [x] 文章二维码，扫一扫，手机阅读
- [x] 文档采集功能优化
    - [x] 增加HTML标签排除功能：`<exclude></exclude>`，如要排除标签`h5`以及class为`hello`、id为"book"的HTML内容，写法是`<exclude>h5,.hello,#book</exclude>`
    - [x] 文档图片采集优化，支持svg等缩图图片格式和base64的图片采集
- [x] 增加全书指定字符替换功能
- [x] 使用 elasticsearch 实现全文搜索（在`管理后台`->`配置管理`进行设置）
    - [x] 搜索功能，支持搜索书籍和全站文档
    - [x] elasticsearch 只返回搜索结果的id，不返回大量的数据
    - [x] 文章、搜索结果页关键字高亮
    - [x] elasticsearch分词
    - [x] 实时索引
        - [x] 删除文档，同时删除文档对应的索引
        - [x] 书籍公有和私有之间转换，同步更新索引中书籍的公有和私有状态
        - [x] 发布文档，实时更新对应的书籍对应文档的全量索引
        - [x] 更新书籍信息，同步更新书籍的索引
        - [x] 删除书籍，同步删除概述及的所有相关文档
        - [x] 管理后台控制默认搜索的是文档还是书籍
    - [x] 文档内的搜索，使用elasticsearch
- [x] 在书籍编辑页面可以克隆或者是上传markdown
- [x] 文章内容页顶部显示 作者、发布时间、更新时间、浏览量、分享人
- [x] 新建和编辑项目，支持添加原作者和原作者链接 
- [x] 文档文章内容，顶部标题下显示信息
- [x] 管理后台控制第三方登录的显示与隐藏
- [x] HTML table 渲染问题优化（把`editormd.js`中的`breaks`设置为false）

```
sudo docker run -it -p 9300:9300 -p 9200:9200 --restart always -v /Users/TruthHun/elasticsearch/data:/usr/share/elasticsearch/data -v /Users/TruthHun/elasticsearch/config:/usr/share/elasticsearch/config --name bookstack-search truthhun/elasticsearch:6.2.4.ik
sudo docker run -it -p 9300:9300 -p 9200:9200 -v /Users/TruthHun/elasticsearch/data:/usr/share/elasticsearch/data --name bookstack-search truthhun/elasticsearch:6.2.4.ik
```

## V1.5 升级日志
- [x] 修复：文档项目删除时间过长进而导致删除失败的Bug（启用了MySQL的事务，但事务中SQL语句有select字句查询造成的问题）
- [x] 修复：项目成员列表显示不全的Bug(分页问题导致) [#25](https://github.com/TruthHun/BookStack/issues/25)
- [x] 修复：文档项目标识正则匹配规则不正确的问题
- [x] 优化：分类在筛选文档项目的时候，SEO优化，以文档分类作为`title`等，不再以首页的文案作为`title`
- [x] 优化：一键采集文档项目，自动检测并下载图片
- [x] 优化：恢复文档模板功能
- [x] 优化：文档中，图片不再使用带http的URL绝对路径，以解决更换域名后写死的URL找不到图片
- [x] 新增：书籍推荐，在封面加上"推荐"图标标志。
- [x] 新增：`Git Clone` 的方式导入项目
    - [x] 编辑文档图片需要处理
    - [x] 阅读页面图片需要处理
    - [x] 导出文档图片需要处理
    - [x] 项目导入的图片需要处理
- [x] 优化：文档阅读体验优化
    - [x] 文档阅读页面左侧章节菜单，可展开和收起
    - [x] 键盘左右方向键按键切换文档上下章节
    - [x] 文档目录全部展开，所有章节一目了然
    - [x] 移除`jstree`插件（因为使用该插件，在用户网速比较慢的情况下左侧章节目录排版会出现错乱，影响体验）
    - [x] 已阅读章节，`打勾`标识出来，以便知道哪些章节已读哪些章节未读
    - [x] 章节目录跟随阅读进度定位位置
- [x] 新增：版本控制(在)
    - [x] 文档编辑历史，使用文件存储的方式进行记录，不存入数据库.
    - [x] 版本控制，在`<bookstack-git></bookstack-git>`标签内添加文案用以提交版本说明。如`<bookstack-git>first commit</bookstack-git>`等同于`git commit -m "first commit"`
    - [x] 删除版本记录的时候要同时删除版本文件
    - [x] 删除文档项目时同时删除项目所有的相关文档章节版本记录
    - [x] 删除单个文档章节以及删除上一级文档章节，则被删除的文档章节的历史版本记录同样要删除
- [x] `SUMMARY.md`功能扩展，输入`<bookstack-auto></bookstack-auto>`，获取所有文档章节标识
    
    


<a name="v1.4"></a>
## V1.4 升级日志
- [x] 修复：由于js使用严格模式(`use strict`)，导致文档目录收起之后无法展开
- [x] 修复：采集内容，URL链接和图片链接补全不正确
- [x] 优化：书籍离线文档生成加锁优化，移除`app.conf`中的`GenerateInterval`配置项
- [x] 优化：PDF、epub和mobi等电子书生成工具 [Converter](https://github.com/TruthHun/converter)，在生成电子书时，自动生成封面。
- [x] 优化：`<bookstack-summary>`标签的一键排序和批量创建文档的功能。
- [x] 移除：生成PDF的时候，移除HTML中的Markdown TOC。
- [x] 新增：提供`Dockerfile`，让部署程序更快更简单。在下载`BookStack`程序的时候，请下载Docker版，压缩包内含有`Dockerfile`文件。
- [x] 新增：爬虫一键采集功能，采集整理书籍，一步到位！


---------

本次更新，新增了数据表初始数据，旧版本用户，直接执行`./BookStack install`操作，对数据库表进行升级（不会影响原有表数据和结构）。



<a name="v1.3"></a>
## V1.3 开发升级预告
- [x] 新增：用户阅读记录和阅读进度
- [x] 新增：阅读书签功能，以便读者标记阅读位置
- [x] 新增：书籍详情页和文档内容页增加分享功能（由于百度分享等现有分享代码不支持`https`，所以使用本地化百度分享源码解决方案 https://github.com/hrwhisper/baiduShare ）
- [x] 新增：使用KaTeX（ https://github.com/Khan/KaTeX ），扩展对数学公式的支持
- [x] 优化：更新HTML转markdown工具[html2md](https://github.com/TruthHun/html2md)，强化转化效果
- [x] 修复：文档内URL链接大小写问题优化 [issue#20](https://github.com/TruthHun/BookStack/issues/20)
- [x] 修复：友链唯一索引问题(默认的字段varchar类型长度(255)过长，导致部分MySQL数据库无法生成唯一索引)
- [x] 修复：文档内容更新了，执行发布文档操作的时候，文档更新部分的内容仍然不显示的问题



<a name="v1.2"></a>
## V1.2 升级日志(功能增强，已于2018-04-07完成)
- [x] 修复图片存储路径不正确的问题
- [x] 正确输入文档项目标识和登录密码才能删除文档项目，以避免误删操作
- [x] 增加移动端搜索入口
- [x] 扩展采集功能，增加`DIY模式`，以采集提取页面的指定内容
- [x] 增加文档分类功能（工作量最大的一项，还新增了分类数据表。用户都不知道自己需要什么，但是却知道自己不需要什么，所以必须要有个分类来引导用户查找自己需要的资料；前端隐藏暂时没有书籍的分类）
- [x] sitemap的`changefreq`，调整为`weekly`
- [x] 项目名称，SEO时，默认加上书名号
- [x] 用户个人主页、收藏、关注、粉丝等
- [x] 友链管理




<a name="v1.1"></a>
## V1.1 升级日志(已于2018-03-04完成开发)
当前版本，已经适合用于正式产品。数据表结构没有变更，可以直接从v1.0升级。

FIX:
- [x] 增加备案链接链到工信部。
- [x] 文档阅读页面缺少了统计代码，已加上。
- [x] 解决给文档打分时分值错误的问题。
- [x] 一键导入和一键拉取markdown项目时，如果出现相同identity的文档，则执行更新，否则为新录入
- [x] 一键拉取项目，支持任何来源的zip压缩的markdown项目的拉取
- [x] 无刷新加载上下篇阅读文档，优化阅读体验
- [x] 移除SEO等Go文件中硬编码的"bookstack.cn"的域名(因为BookStack，一开始是打算自用的，所以当时写死了)
- [x] 登录和注册验证码优化（使用Beego自带的验证码体系：https://github.com/astaxie/beego/tree/master/utils/captcha）
- [x] 支持本地化存储（改动了很多地方，具体改动，请`git log`查看）。在app.conf中增加了`store_type`配置项，以扩展存储类型，目前扩展的存储类型有本地存储(`local`)和阿里云OSS存储(`oss`)，更多存储类型(`七牛云存储(qiniu)、腾讯云存储(cos)、百度云存储(bos)、又拍云存储(upyun)`)持续开发中.
- [x] 分页优化
- [x] 解决角色名称有时不显示的问题
- [x] 解决`导入项目`和`拉取项目`，项目中的图片、文档间的链接不正确的问题，目前兼容绝大多数各种姿势的markdown项目导入和拉取

