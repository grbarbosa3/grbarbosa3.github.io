---
title: "Home"
---

<!-- Inline carousel-only styles (kept here so they don't clash with grid) -->
<style>
  .carousel { position: relative; overflow: hidden; }
  .carousel-track {
    display: flex;
    gap: 1rem;
    flex-wrap: nowrap;        /* keep in one row */
    overflow-x: auto;
    scroll-behavior: smooth;
    padding-bottom: .25rem;
    -ms-overflow-style: none; /* IE/Edge */
    scrollbar-width: none;    /* Firefox */
  }
  .carousel-track::-webkit-scrollbar { display: none; } /* WebKit */
  .carousel .card { flex: 0 0 300px; } /* slide width */
</style>

<section id="about" class="section">
  <div class="about-container">
    <img src="{{ '/assets/images/me.jpeg' | relative_url }}"
         alt="Michael Shoemaker"
         class="profile-pic">

    <div class="about-text">
      <h1>Welcome to my portfolio! I'm Guilherme Barbosa</h1>
      <p>Senior Data Analyst | Data Engineer | Airspace Engineer Student | .5x Programmer</p>
      <p>I build practical, production-like data solutions - orchestration, storage, transformations, serving, and analytics - then explain the decisions behind them.</p>
      <p><strong>Core skills:</strong> Python · SQL · Power BI · dbt · Airflow · Snowflake · BigQuery · Docker · GCP</p>

      <p class="social-links">
        <a href="https://www.linkedin.com/in/guilhermerbarbosa" target="_blank" aria-label="LinkedIn">
          <i class="fa-brands fa-linkedin"></i>
        </a>
      </p>
    </div>
  </div>
</section>

<!-- ===================== Projects ===================== -->
<section id="projects" class="section">
  <div class="section-header">
    <h2>🚀 Projects</h2>
    <a class="view-all" href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener">All repos →</a>
  </div>

  {% assign projects_count = site.data.projects | size %}
  {% if projects_count > 4 %}
    <div class="carousel">
      <button class="scroll-btn left" data-target="#projects-track" aria-label="Scroll projects left">‹</button>
      <div id="projects-track" class="carousel-track" role="region" aria-label="Projects list">
        {% for item in site.data.projects %}
        <article class="card">
          <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open project">
            <img src="{{ item.image | default: '/assets/images/placeholder_project.jpg' | relative_url }}"
                 alt="{{ item.title | escape }} thumbnail"
                 loading="lazy"
                 {% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
          </a>
          <div class="card-body">
            <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
            <p class="card-text">{{ item.description }}</p>
            {% if item.stack %}<p class="card-tags">{{ item.stack }}</p>{% endif %}
            <div class="card-actions">
              {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
              <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Open</a>
            </div>
          </div>
        </article>
        {% endfor %}
      </div>
      <button class="scroll-btn right" data-target="#projects-track" aria-label="Scroll projects right">›</button>
    </div>
  {% else %}
    <div class="gallery">
      {% for item in site.data.projects %}
      <article class="card">
        <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open project">
          <img src="{{ item.image | default: '/assets/images/placeholder_project.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail" loading="lazy">
        </a>
        <div class="card-body">
          <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
          <p class="card-text">{{ item.description }}</p>
          {% if item.stack %}<p class="card-tags">{{ item.stack }}</p>{% endif %}
          <div class="card-actions">
            {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
            <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Open</a>
          </div>
        </div>
      </article>
      {% endfor %}
    </div>
  {% endif %}
</section>

<!-- ===================== Videos ===================== -->
<section id="videos" class="section">
  <div class="section-header">
    <h2>🎥 Videos</h2>
    <a class="view-all" href="https://youtube.com/{{ site.youtube_channel }}" target="_blank" rel="noopener">Channel →</a>
  </div>

  {% assign videos_count = site.data.videos | size %}
  {% if videos_count > 4 %}
    <div class="carousel">
      <button class="scroll-btn left" data-target="#videos-track" aria-label="Scroll videos left">‹</button>
      <div id="videos-track" class="carousel-track" role="region" aria-label="Videos list">
        {% for item in site.data.videos %}
        <article class="card">
          <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open video">
            <img src="{{ item.image | default: '/assets/images/placeholder_video.jpg' | relative_url }}"
                 alt="{{ item.title | escape }} thumbnail"
                 loading="lazy"
                 {% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
          </a>
          <div class="card-body">
            <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
            {% if item.note %}<p class="card-text">{{ item.note }}</p>{% endif %}
            <div class="card-actions">
              {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
              <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Watch</a>
            </div>
          </div>
        </article>
        {% endfor %}
      </div>
      <button class="scroll-btn right" data-target="#videos-track" aria-label="Scroll videos right">›</button>
    </div>
  {% else %}
    <div class="gallery">
      {% for item in site.data.videos %}
      <article class="card">
        <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open video">
          <img src="{{ item.image | default: '/assets/images/placeholder_video.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail" loading="lazy">
        </a>
        <div class="card-body">
          <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
          {% if item.note %}<p class="card-text">{{ item.note }}</p>{% endif %}
          <div class="card-actions">
            {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
            <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Watch</a>
          </div>
        </div>
      </article>
      {% endfor %}
    </div>
  {% endif %}
</section>

<!-- ===================== Articles ===================== -->
<section id="articles" class="section">
  <div class="section-header">
    <h2>✍️ Articles</h2>
    <a class="view-all" href="https://medium.com/@{{ site.medium_username }}" target="_blank" rel="noopener">Medium →</a>
  </div>

  {% assign articles_count = site.data.articles | size %}
  {% if articles_count > 4 %}
    <div class="carousel">
      <button class="scroll-btn left" data-target="#articles-track" aria-label="Scroll articles left">‹</button>
      <div id="articles-track" class="carousel-track" role="region" aria-label="Articles list">
        {% for item in site.data.articles %}
        <article class="card">
          <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open article">
            <img src="{{ item.image | default: '/assets/images/placeholder_article.jpg' | relative_url }}"
                 alt="{{ item.title | escape }} thumbnail"
                 loading="lazy"
                 {% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
          </a>
          <div class="card-body">
            <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
            {% if item.subtitle %}<p class="card-text">{{ item.subtitle }}</p>{% endif %}
            <div class="card-actions">
              {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
              <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Read</a>
            </div>
          </div>
        </article>
        {% endfor %}
      </div>
      <button class="scroll-btn right" data-target="#articles-track" aria-label="Scroll articles right">›</button>
    </div>
  {% else %}
    <div class="gallery">
      {% for item in site.data.articles %}
      <article class="card">
        <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open article">
          <img src="{{ item.image | default: '/assets/images/placeholder_article.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail" loading="lazy">
        </a>
        <div class="card-body">
          <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
          {% if item.subtitle %}<p class="card-text">{{ item.subtitle }}</p>{% endif %}
          <div class="card-actions">
            {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
            <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Read</a>
          </div>
        </div>
      </article>
      {% endfor %}
    </div>
  {% endif %}
</section>

<!-- Tiny helper script for arrow buttons -->
<script>
(function () {
  function init(btn) {
    var targetSel = btn.getAttribute('data-target');
    var track = document.querySelector(targetSel);
    if (!track) return;
    var step = Math.max(300, Math.floor(track.clientWidth * 0.9));

    btn.addEventListener('click', function () {
      track.scrollBy({ left: btn.classList.contains('left') ? -step : step, behavior: 'smooth' });
    });

    function update() {
      var max = track.scrollWidth - track.clientWidth - 1;
      var x = track.scrollLeft;
      var leftBtn = track.parentElement.querySelector('.scroll-btn.left');
      var rightBtn = track.parentElement.querySelector('.scroll-btn.right');
      if (leftBtn) leftBtn.disabled = x <= 0;
      if (rightBtn) rightBtn.disabled = x >= max;
    }
    track.addEventListener('scroll', update, { passive: true });
    window.addEventListener('resize', update);
    update();
  }
  document.querySelectorAll('.scroll-btn').forEach(init);
})();
</script>
