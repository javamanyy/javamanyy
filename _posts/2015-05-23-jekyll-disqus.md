---
layout: post
title: Jekyll中添加评论系统
cover: cover.jpg
date:   2015-05-23 12:00:00
categories: 其他
---



创建Disqus账号
----------


注册disqus账号https://disqus.com 并登陆。
点击右上角头像边上的settings按钮。弹出菜单选择'Add Disqus To site'
打开Add Disqus to your site的页面： 
Site Name 
随便填一个名字就好了
Choose your unique Disqus URL
这里就是后面引用的名字啦。例如：javaman.disqus.com
点击Finish就好。

----------


添加到Jekyll中
-------------

- _config.yml中添加 disqussite: javaman

- _includes目录下新建comments.ext文件

- 内容显示页面添加评论


创建Disqus账号
----------


注册disqus账号https://disqus.com 并登陆。
点击右上角头像边上的settings按钮。弹出菜单选择'Add Disqus To site'
打开Add Disqus to your site的页面： 
Site Name 
随便填一个名字就好了
Choose your unique Disqus URL
这里就是后面引用的名字啦。例如：javaman.disqus.com
点击Finish就好。

----------


添加到Jekyll中
-------------

- _config.yml中添加 disqussite: javaman

- _includes目录下新建comments.ext文件

- 内容显示页面添加评论

```javascript
<div id="disqus_thread"></div> 	 
<script type="text/javascript">
    var disqus_shortname = '{{site.disqussite}}';
    (function() {
      var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
      dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
    				 (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body'[0]).appendChild(dsq);
</script> 	 
<noscript>Please enable JavaScript to view the <a href="http://disqus.com/?ref_noscript">comments powered by Disqus.</a>
</noscript>
<a href="http://disqus.com" class="dsq-brlink">comments powered by <span class="logo-disqus">Disqus</span></a>
```

```javascript
<section class="comments">
	{% if page.comments %}
		{% include comments.ext %}
	{% endif %}
</section>
```

