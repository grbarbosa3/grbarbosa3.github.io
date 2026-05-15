---
title: "Home"
---

<style>
  .section {
    width: 100%;
    max-width: 1100px;
    margin: 0 auto;
    padding: 2.5rem 2rem;
    box-sizing: border-box;
  }

  .about-container {
    width: 100%;
    display: grid;
    grid-template-columns: 220px 1fr;
    gap: 2.5rem;
    align-items: start;
    box-sizing: border-box;
  }

  .profile-pic {
    width: 190px;
    height: 190px;
    border-radius: 50%;
    object-fit: cover;
    margin-top: 0.4rem;
  }

  .about-text {
    width: 100%;
    max-width: 780px;
  }

  .about-text h1 {
    margin-top: 0;
    margin-bottom: 0.7rem;
    font-size: 2rem;
    line-height: 1.2;
    text-align: left;
  }

  .location {
    margin-top: 0;
    margin-bottom: 1rem;
    font-size: 0.95rem;
    opacity: 0.75;
    text-align: left;
  }

  .headline {
    display: inline-block;
    margin: 0.3rem 0 1.4rem 0;
    padding: 0.55rem 0.85rem;
    font-size: 1rem;
    font-weight: 600;
    line-height: 1.4;
    text-align: left;
    border-left: 4px solid #2563eb;
    background: rgba(37, 99, 235, 0.08);
    border-radius: 8px;
  }

  .description {
    text-align: left;
    line-height: 1.6;
    margin-top: 0;
    margin-bottom: 1rem;
  }

  .skills {
    text-align: left;
    line-height: 1.6;
    margin-top: 1rem;
    margin-bottom: 1.4rem;
  }

  .english-version {
    margin-top: 1.5rem;
    padding-top: 1rem;
    border-top: 1px solid rgba(0, 0, 0, 0.12);
    font-size: 0.9rem;
    opacity: 0.85;
    line-height: 1.5;
  }

  .english-version p {
    margin: 0.35rem 0;
    text-align: left;
  }

  .english-version-title {
    font-weight: 700;
    margin-bottom: 0.6rem !important;
  }

  .social-links {
    text-align: left;
    margin-top: 1.2rem;
  }

  .social-links a {
    font-size: 1.4rem;
    text-decoration: none;
  }

  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }

  @media (max-width: 768px) {
    .section {
      padding: 2rem 1.25rem;
    }

    .about-container {
      grid-template-columns: 1fr;
      gap: 1.5rem;
    }

    .profile-pic {
      width: 160px;
      height: 160px;
      margin: 0 auto;
      display: block;
    }

    .about-text {
      max-width: 100%;
    }

    .about-text h1,
    .location,
    .headline,
    .description,
    .skills,
    .english-version p,
    .social-links {
      text-align: left;
    }
  }
</style>

<section id="about" class="section">
  <div class="about-container">
    <img src="{{ '/assets/images/me.png' | relative_url }}"
         alt="Guilherme Barbosa"
         class="profile-pic">

    <div class="about-text">
      <h1>Olá, eu sou Guilherme Barbosa</h1>

      <p class="location">📍 São José dos Campos, Brazil</p>

      <p class="headline">
        Analista de Dados | Engenharia de Dados | Engenharia Aeronáutica
      </p>

      <p class="description">
        Construo soluções de dados, desde ingestão e orquestração até transformação,
        análise, dashboards e geração de insights para direcionamentos e acompanhamentos.
      </p>

      <p class="description">
        Possuo mais de 5 anos de experiência, atualmente expandindo meus conhecimentos com Engenharia de Dados para entregar soluções para setores de tecnologia, aviação e outros diversos contextos de negócios, incluindo E-Commerce, Finanças, Education e Marketing.
      </p>

      <p class="skills">
        <strong>Principais habilidades:</strong> Python · SQL · Power BI · dbt · Airflow · Snowflake · BigQuery · Docker · GCP
      </p>

      <div class="english-version">
        <p class="english-version-title">English version</p>

        <p>
          Data Analyst | Data Engineering | Aerospace Engineering
        </p>

        <p>
          I build practical, production-oriented data solutions, from ingestion and orchestration
          to transformations, analytics, dashboards, and business insights.
        </p>

        <p>
          Data professional with 5+ years of experience, currently transitioning into Data Engineering to deliver solutions across tech, aviation, and diverse business domains including E-Commerce, Finance, Education and Marketing.
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
    <a class="view-all" href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener">
      Ver todos repositórios (All repos) →
    </a>
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
<!-- ===================== Articles  ===================== -->
<section id="articles" class="section">
  <div class="section-header">
    <h2>📖 Learn</h2>
    <a class="view-all" href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener">
      Ver todos repositórios (All repos) →
    </a>
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
