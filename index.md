---
layout: default
---

<img src="assets/img/home.png" alt="home">

# homepage

words someone said:
<div id="randomCitation"></div>
<br>
refresh the page for more comical quotes
<br>
[[about me]](./about.html)

---

<img src="assets/img/statues.png" alt="home">

<h1>posts</h1>
<p>this is what I have been up to lately</p>

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

<script>
<!-- Code for random citation -->
  document.addEventListener('DOMContentLoaded', function() {
      const citations = [
          { text: "There is a plot. What would be the point of just a bunch of things?", author: "David Lynch" },
          { text: "This is a textbook way too. It's just my textbook.", author: "Andrew Gelman" },
          { text: 'That\'s right. My own beliefs are unbelievable.', author: "John C. Lilly"},
          { text: "Then he unsmiled his lips and got real plural on me. 'We'll let you know.'", author: "Norm Macdonald"}
      ];

      function getRandomCitation() {
          const randomIndex = Math.floor(Math.random() * citations.length);
          return citations[randomIndex];
      }

      function displayCitation() {
          const citation = getRandomCitation();
          document.getElementById('randomCitation').innerHTML = `<blockquote> <i>${citation.text}
  <div style="text-align: right"> -${citation.author} </div> </i> </blocquote>`;
      }

      displayCitation();
  });
</script>