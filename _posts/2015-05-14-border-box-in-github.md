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

---

说一下自己的拿到功能结构图的整个思考过程，主要从以下几个方面思考。
<br><mark>Part   one</mark>
   <br>**产品定位分析：**[border-box post]
   <br>No.1  微记，通过图片和文字为家庭成员记录他们每一刻、每一天的生活点滴，创造全家人的共享记忆；
<br><mark>Part   two</mark>
   <br>**界面功能结构分析：**[border-box post]
   <br>**No.1**  四个常规tab（家庭微记、家人、家书、我的），和添加微记botton；
   <br>**No.2**  用于用户及时发布动态消息，包括用户头像，发布时间，动态内容（图片、文字）；
   <br>**No.3 ** 更加注重用户隐私，只有点赞，不包含评论、转发等分享行为；
   <br>**No.4 ** 加入日历功能，方便用户及时查看当天动态；
<br><mark>Part   three</mark>
   <br>**相似功能分析界面分析**[border-box post]
   <br>**No.1** 朋友圈、qq空间
      <br>A、相同点：及时发布动态消息，包含用户头像，发布时间，动态内容（图片、文字）；
      <br>B、不同点：
          <br>a、没有评论、转发的分享功能；
          <br>b、朋友圈和qq空间更在于分享，微记更在于记录微记对于用户的每一条状态
            更加重视，不是单纯的下拉刷新，一条条动态简单粗暴的刷过去；
   <br>**No.2 ** 日记类功能app
      <br>A、相同点：真正的回归记录，把重点放在用户的每一篇、每一天生活记录，记录方式、
               记录目的更加明确，使用户感受到自己每天的生活都在被记录；
      <br>B、不同点：
          <br>a、日记大多在于记录自己个人生活，微记在于记录家庭每一个成员的生活，
            使他们之间达到共享的家庭状态。关于自己的记录内容，对于家庭成员，
            可以选择公开或不公开的方式；

---

综上，对于微记的原型界面设计有了明确的方案
<br><mark>记录方式</mark>
  <br>No.1  每一条微记内容
       <br>A、微记更靠近日记的记录的方式,每一条微记以块状形式，独立呈现，包含用户头像、用户昵称、
         发表时间、发表内容
         <br>【针对发表内容，说明一下，根据功能要求，用户最后呈现发表状态，共有三种
           <br><br><br>a、图片+文字
           <br><br>b、纯图片
           <br>c、纯文字
           <br>所以要出三种状态原型】
<br>No.2  多条微记的呈现形式：
        <br>A、上下滑动同一天不同时刻的所有家庭成员所发表的微记
        <br>B、向左滑动，后一天不同时刻的所有家庭成员所发表的微记
        <br>C、向右滑动，前一天不同时刻的所有家庭成员所发表的微记
 
<br><mark>四个常规tab</mark>（第一本版本中，“我的”因当时特殊考虑，没有放上去，不影响整体交互体验效果）
        <br>之所以选择将4个tab包括添加微记botton放在页面的顶部，是因为，如果4个tab放在界面底部。当         用户上滑查看一天家庭成员的动态，用户手指的滑动与界面的交互位置和4个tab放在底部的位置,会有一些重合，引发用户误点，影响用户体验。
       <br>【好吧，这个想法，自己现在看起来，确实是有点“想多了”
        <br>不过，在这里，我要说明一下我这里所犯的错误--作为交互设计师，自己在空想用户使用产品的过         程，虽然很多时候我们需要模拟用户使用产品的场景，也许用户的大多使用习惯，是我们在过去的         经验中、在自己的使用场景中、在书本中，是可预见的，但是有时候自信的一味的空想模拟，就会         忽视很多的用户细节，如果被忽视的细节一旦多了，那差距想必会影响整个产品的用户体验。
        后话，自己找到几款需要下滑查看动态，并且tab在界面底部的app，推荐自己的一些不同年龄、         不同性别的朋友使用，并悄悄观察他们的交互状态、体验效果，事实上，大部分的用户，当他们手         指准备点击屏幕上滑时，大家会刻意回避这个区域，只要标签栏高度合理，界面交互范围符合用户手势舒服的合理区域，由于上滑，造成误点的情况几乎没有】
 
<br><mark>关于添加微记的botton</mark>
        <br>由于把四个tab放在了顶部的最上面，考虑到视觉平衡，一开始准备将botton放在最中间，但是如         果将botton放在中间，用户点击起来相对比较麻烦，所以，综合考虑来看，决定将botton放在最右         边，一方面，方便用户点击。另一方面，微记上面需要加上当天的日期，避免整个微记界面中间拥挤的情况。
 
<br><mark>日历botton</mark>
        <br>因为将当天日期放在了每天最新微记的上面，所以，便将日历放在了其旁边，同一性质，都在于根据时间查看当天微记内容


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