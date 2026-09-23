---
layout: default
title: Home
---

<div class="hero">
  <h2>Welcome to My Journey</h2>
  <p>Documenting my pre-nursing studies, AI in Bio research, and tech projects on GitHub.</p>
</div>

<div class="highlights">
  <div class="card">
    <h3>🎓 Education</h3>
    <p>Pre-Nursing Major with a Minor in Public Health Informatics at The University of Memphis</p>
  </div>
  <div class="card">
    <h3>🎯 Target Career</h3>
    <p>I would like to become a Intensive Care Unit Nurse (ICU Nurse)</p>
  </div>
  <div class="card">
    <h3>💻 Current Focus</h3>
    <p>Exploring AI applications in biology & building open-source projects</p>
  </div>
</div>

<hr />

### 📝 Recent Posts

<ul class="post-list">
{% for post in site.posts limit:3 %}
  <li class="post-item">
    <a href="{{ post.url | relative_url }}" class="post-title">{{ post.title }}</a>
    <span class="post-date">{{ post.date | date: "%b %d, %Y" }}</span>
  </li>
{% else %}
  <p>No blog posts published yet. Stay tuned!</p>
{% endfor %}
</ul>