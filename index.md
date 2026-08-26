---
title: Home
description: The songs defining the summer.
---

<section class="hero">
  <p class="eyebrow">The seasonal soundtrack</p>
  <h1>Top 10 Songs<br><em>of the Summer</em></h1>
  <p class="hero-copy">A personal countdown of the tracks that captured the energy, emotion, and atmosphere of the season.</p>
  <a class="button" href="#countdown">Explore the countdown <span>↓</span></a>
</section>

<section class="intro" id="countdown">
  <div>
    <p class="eyebrow">The collection</p>
    <h2>Ten tracks.<br><em>One unforgettable season.</em></h2>
  </div>
  <p>Use the song pages to share your reviews, add cover art, and assign your own star rating to every entry.</p>
</section>

<section class="song-grid">
  {% assign songs = site.songs | sort: "rank" %}
  {% for song in songs %}
    <a class="song-card" href="{{ song.url | relative_url }}">
      <div class="card-art placeholder-art">
        <span>{{ song.rank | prepend: "0" | slice: -2, 2 }}</span>
      </div>
      <div class="card-meta">
        <span class="rank">#{{ song.rank }}</span>
        <h3>{{ song.title }}</h3>
        <p>{{ song.performer }}</p>
      </div>
      <span class="arrow">↗</span>
    </a>
  {% endfor %}
</section>
