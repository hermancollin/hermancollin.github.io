---
layout: default
---

![home](assets/img/home.png)

# homepage

things people said:

> *There is a plot. What would be the point of just a bunch of things?*
<div style="text-align: right"> -David Lynch </div>
<div style="text-align: center"> *** </div>

>*This is a textbook way too. It’s just my textbook.*
<div style="text-align: right"> -Andrew Gelman </div>

[[about me]](./about.html)

---

![home](assets/img/statues.png)

# posts
this is what I have been up to lately

{% for post in site.posts %}
  <article>
    <h3>
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h3>
    <time datetime="{{ post.date | date: '%Y-%m-%d' }}">{{ post.date | date_to_long_string }}</time>
    | <i> {{ post.abstract }} </i>
    <!-- {{ post.content }} -->
  </article>
  
{% endfor %}