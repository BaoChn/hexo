## Build-up

https://hexo.io/zh-cn/docs/
https://nodejs.org/zh-cn/download
https://git-scm.com/

$ npm install -g hexo-cli

$ npm install hexo

<!-- git clone -b main https://github.com/anzhiyu-c/hexo-theme-anzhiyu.git themes/anzhiyu -->
<!-- https://github.com/anzhiyu-c/hexo-theme-anzhiyu/releases -->
<!-- npm i hexo-theme-anzhiy -->

> # Extensions  
> ## Plugins: https://hexo.io/plugins/  
> ## Themes: https://hexo.io/themes/  
> theme: anzhiyu  

$ npm install hexo-renderer-pug hexo-renderer-stylus --save

hexo cl
hexo g
hexo s

依赖树信息 npm ls

## Write

新建文章
hexo new "title"  
草稿箱
hexo new draft "title"  
发布草稿
hexo publish "title"  
空白页
hexo new page "title"

插入图片
> {% image (url), alt=(描述) %}  

插入提示
> {% note info flat %}文本{% endnote %}  

插入链接块
> {% link 标题,描述,(url) %}  

按键
{% kbd (按键号) %}

{% image , alt= %}  
{% kbd  %}

## Album
album_list:
    - date: 2000/00/00 01:00:00
      content: 描述
      image:
        - (url)
    - date: 2000/00/00
      content: 描述
      address: 地址
      from: 来源
      image:
        - 