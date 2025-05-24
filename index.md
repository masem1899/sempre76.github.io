---
layout: default
title: PySty
show_side_panel: false
---

<script>
  const showSidePanel = false; // set this based on the page
  if (!showSidePanel) {
    document.querySelector('.side-panel').style.display = 'none';
  }
</script>

# News
<div class="blog-list">
    <ul>
    {% for post in site.posts %}
        <li>
            <a href="{{ post.url }}">{{ post.title }}</a>
            <small>({{ post.date | date: "%Y-%m-%d}})</small>
        </li>
    {% endfor %}
    </ul>
</div>