---
title: "Home"
---

<style>
  .location {
    margin-top: -0.4rem;
    margin-bottom: 1rem;
    font-size: 0.95rem;
    opacity: 0.75;
  }

  .english-version {
    margin-top: 1.5rem;
    font-size: 0.9rem;
    opacity: 0.85;
    line-height: 1.5;
  }

  .english-version p {
    margin: 0.3rem 0;
  }

  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }
</style>

<section id="about" class="section">
  <div class="about-container">
    <img src="{{ '/assets/images/me.jpeg' | relative_url }}"
         alt="Guilherme Barbosa"
         class="profile-pic">

    <div class="about-text">
      <h1>Olá, eu sou Guilherme Barbosa</h1>

      <p class="location">São José dos Campos, Brazil 🇧🇷</p>

      <p class="headline">
        Analista de Dados | Engenharia de Dados | Estudante de Engenharia Aeronáutica
      </p>

      <p>
        Construo soluções práticas de dados, desde ingestão e orquestração até transformação,
        análise, dashboards e geração de insights para tomada de decisão.
      </p>

      <p>
        Profissional de dados com mais de 5 anos de experiência, atualmente expandindo meus conhecimentos com Engenharia de Dados para entregar soluções para setores de tecnologia, aviação e           outros diversos contextos de negócios, incluindo E-Commerce, Finanças, Education e Marketing.
      </p>

      <p><strong>Principais habilidades:</strong> Python · SQL · Power BI · dbt · Airflow · Snowflake · BigQuery · Docker · GCP</p>

      <div class="english-version">
        <p><strong>🇺🇸 English version</strong></p>

        <p>
          Data Analyst | Data Engineering | Aerospace Engineering Student
        </p>

        <p>
          I build practical, production-oriented data solutions, from ingestion and orchestration
          to transformations, analytics, dashboards, and business insights.
        </p>

        <p>
          Data professional with 5+ years of experience, currently transitioning into Data Engineering to deliver solutions across tech, aviation, and diverse business domains including E-                Commerce, Finance, Education and Marketing.
        </p>
      </div>

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

  <div class="gallery">
    {% for item in site.data.projects %}
    <article class="card">
      <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open project">
        <img src="{{ item.image | default: '/assets/images/placeholder_project.jpg' | relative_url }}"
             alt="{{ item.title | escape }} thumbnail"
             loading="lazy"
             {% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
      </a>

      <div class="card-body">
        <h3 class="card-title">
          <a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a>
        </h3>

        <p class="card-text">{{ item.description }}</p>

        {% if item.stack %}
        <p class="card-tags">{{ item.stack }}</p>
        {% endif %}

        <div class="card-actions">
          {% if item.screenshot %}
          <a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>
          {% endif %}

          <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Open</a>
        </div>
      </div>
    </article>
    {% endfor %}
  </div>
</section>
