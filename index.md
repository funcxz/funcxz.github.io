---
layout: page
title: Welcome
tagline: to functional exercises
---
{% include JB/setup %}

## About   

My name is Denys Kholod and I live in Kiev, Ukraine where I write software for enterprise.   
At leisure time I like to learn functional programing, tools, languages and related ecosystems. Sometimes I use F#, Scala and Clojure to support my daily activities but primarily it is C# that I do for production.   
   
This is my micro-blog and code snippets library that I use to learn and stay hands-on.   
During my regular functional exercises I will train to solve one specific problem using different languages with functional attitude, using the best they can provide.
   
   
<p>
  <a href="https://twitter.com/dkholod" class="twitter-follow-button" data-show-count="false">Follow @dkholod</a>
  <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0];if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src="//platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");</script>
</p>

<p>
  <a href="http://www.linkedin.com/in/dkholod" ><img src="http://www.linkedin.com/img/webpromo/btn_profile_bluetxt_80x15.gif" width="80" height="15" border="0" alt="View Denys Kholod's profile on LinkedIn"></a>
</p>

## Posts
   
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
