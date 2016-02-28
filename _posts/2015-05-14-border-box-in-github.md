---
layout: post
title: 麦粒-其产品原型设计的交互思考过程（一）
---

![layout borken by border-boxing](/images/20150514-box-model.png)

当我拿到产品或者界面功能结构图时，我首先会做以下三点考虑：
<br>1st：该产品定位是什么，我希望用户拥有什么样的体验【至关重要，考虑到每一个交互的细节问题】
<br>2nd：对界面逻辑功能分析，我需要和那些功能打交道
<br>3rd：竞品分析，或者相似功能界面设计、交互分析
<br>三点思考内容，不分顺序，在思考的过程中，很多时候三点是相互影响、相互渗透的


说一下自己的拿到功能结构图的整个思考过程，主要从以下几个方面思考。
<br><mark>Part   one</mark>
   <br>产品定位分析：[border-box post]
   <br>No.1  微记，通过图片和文字为家庭成员记录他们每一刻、每一天的生活点滴，创造全家人的共享记忆；
<br><mark>Part   two</mark>
   <br>界面功能结构分析：[border-box post]
   <br>No.1  四个常规tab（家庭微记、家人、家书、我的），和添加微记botton；
   <br>No.2  用于用户及时发布动态消息，包括用户头像，发布时间，动态内容（图片、文字）；
   <br>No.3  更加注重用户隐私，只有点赞，不包含评论、转发等分享行为；
   <br>No.4  加入日历功能，方便用户及时查看当天动态；
<br><mark>Part   three</mark>
   <br>相似功能分析界面分析[border-box post]
   <br>No.1  朋友圈、qq空间
      <br>A、相同点：及时发布动态消息，包含用户头像，发布时间，动态内容（图片、文字）；
      <br>B、不同点：
          <br>a、没有评论、转发的分享功能；
          <br>b、朋友圈和qq空间更在于分享，微记更在于记录微记对于用户的每一条状态
            更加重视，不是单纯的下拉刷新，一条条动态简单粗暴的刷过去；
   <br>No.2  日记类功能app
      <br>A、相同点：真正的回归记录，把重点放在用户的每一篇、每一天生活记录，记录方式、
               记录目的更加明确，使用户感受到自己每天的生活都在被记录；
      <br>B、不同点：
          <br>a、日记大多在于记录自己个人生活，微记在于记录家庭每一个成员的生活，
            使他们之间达到共享的家庭状态。关于自己的记录内容，对于家庭成员，
            可以选择公开或不公开的方式；

When @paulirish's [border-box post](http://www.paulirish.com/2012/box-sizing-border-box-ftw/) first came out, it was discussed internally as something that "we should probably do." But then we didn't, because:

> Wouldn't it require we rewrite every element with a width/border/padding?
<br>

> I’m pretty sure the internet would break in half if we added that rule in today.

The main problem was that it wasn't easy to find out which bit of code would need to be changed just by reading them. It felt at the time like a very big refactor project, and just [too big](http://markdotto.com/2014/07/23/githubs-css/#two-bundles) for any single person to tackle.

But every once in a while, you get a new designer onboard, say, someone like me, trying to disturb the water. In my first month, I sent at least 5 pull requests trying to fix box-model weirdnesses in `github/github`.

**We really need it.**

I learned that the rule was something that all the CSS-writers working in the github.com code base want, and we just needed to find a way to do it and not break the internet (well, github.com) at the same time.

After some deliberations, we decided that we would team-ship the rule `* { box-sizing: border-box; }` to just a group of people that volunteered to be in the `@github/box-model-shipperheros` team. These people would live with the broken layout everyday as we use GitHub to build GitHub, and try to fix them one at a time. The code looked like this:

{% highlight erb linenos %}
<%# in the head of application.erb %>
<%= render :partial => "box_model_css" if team_access?(:box_model) %>

<%# in _box_model_css.erb %>
<style type="text/css"> * { box-sizing: border-box; } </style>
{% endhighlight %}

While adding a fix, we would slap on <code>&#64;include box-sizing</code>, with the idea that when we're done, we'd remove them all.

![diagram on the confusing negative margin border padding ](/images/20150514-notification.png)

![holy crap broke the internet](/images/20150514-holy-crap.png)

The whole process took about 4 months, before we decided that we had probably covered 99.9% of the website and that it was safe to ship.

![list of pull requests and issues related to fixing box model](/images/20150514-box-model-prs.png)

And then, we all became happier human beings.

:tada:

---

[Find out more about GitHub's CSS by @mdo](http://markdotto.com/2014/07/23/githubs-css/).