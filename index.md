---
layout: home
title: Deviagames Blog
description: Um blog sobre jogos e tecnologia
---

<div class="hero-section">
  <div class="hero-content">
    <h1 class="hero-title">Bem-vindo ao BLOG</h1>
    <p class="hero-subtitle">Conteúdo de qualidade sobre jogos, tecnologia, programação e criatividade.<br>Descubra, aprenda e compartilhe!</p>
    <a href="#posts" class="hero-btn">Ver posts recentes</a>
  </div>
</div>

## Posts Recentes

<div class="post-list" id="posts">
  {% for post in site.posts %}
    <article class="post-preview">
      <h2>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>
      </h2>
      <div class="post-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">
          {{ post.date | date: "%d/%m/%Y" }}
        </time>
        {% if post.categories.size > 0 %}
          <span class="post-categories">
            em {% for category in post.categories %}
              <a href="{{ '/categories/' | relative_url }}#{{ category | slugify }}">{{ category }}</a>
              {% unless forloop.last %}, {% endunless %}
            {% endfor %}
          </span>
        {% endif %}
      </div>
      <div class="post-excerpt">
        {{ post.excerpt | strip_html | truncatewords: 50 }}
      </div>
      <a href="{{ post.url | relative_url }}" class="read-more">Ler mais →</a>
    </article>
  {% endfor %}
</div> 