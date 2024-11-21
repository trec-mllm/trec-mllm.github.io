<style>
/* Responsive image handling */
.hero-image {
    width: 100%;
    max-width: 800px;
    margin: 0 auto;
    display: block;
    height: auto;
    transition: transform 0.3s ease;
}

/* Responsive typography */
@media (max-width: 768px) {
    h1 { font-size: 1.8rem; }
    h2 { font-size: 1.5rem; }
    h3 { font-size: 1.3rem; }
    p, li { font-size: 1rem; line-height: 1.6; }
}

/* Collapsible sections for mobile */
.collapse-section {
    border: 1px solid #eee;
    border-radius: 8px;
    margin: 1rem 0;
    overflow: hidden;
}

.collapse-header {
    background: #f8f9fa;
    padding: 1rem;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: background-color 0.3s ease;
}

.collapse-header:hover {
    background: #e9ecef;
}

.collapse-content {
    padding: 0 1rem;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease-out;
}

.collapse-content.active {
    max-height: 1000px;
    padding: 1rem;
}

/* Enhanced organizers table */
.organizers-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 24px;
    margin: 20px 0;
}

@media (max-width: 768px) {
    .organizers-table {
        border-spacing: 12px;
    }
    
    .organizers-table tr {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }
    
    .organizers-table td {
        flex: 0 0 50%;
        margin-bottom: 20px;
    }
}

@media (max-width: 480px) {
    .organizers-table td {
        flex: 0 0 100%;
    }
}

.organizers-table td {
    width: 25%;
    text-align: center;
    padding: 12px;
    vertical-align: top;
}

.organizers-table img {
    height: 130px;
    width: 130px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: 16px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
}

.organizers-table img:hover {
    transform: scale(1.05);
}

.name {
    font-size: 16px;
    font-weight: 600;
    color: #1a1a1a;
    margin-bottom: 8px;
}

.affiliation {
    font-size: 14px;
    color: #666;
    line-height: 1.4;
}

/* Back to top button */
.back-to-top {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background: #007bff;
    color: white;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    opacity: 0;
    transition: opacity 0.3s ease;
    cursor: pointer;
}

.back-to-top.visible {
    opacity: 1;
}

@media print {
    .back-to-top {
        display: none;
    }
}
</style>

<script>
// Collapsible sections
document.addEventListener('DOMContentLoaded', function() {
    // Initialize collapsible sections
    const headers = document.querySelectorAll('.collapse-header');
    headers.forEach(header => {
        header.addEventListener('click', () => {
            const content = header.nextElementSibling;
            content.classList.toggle('active');
            const arrow = header.querySelector('.arrow');
            arrow.textContent = content.classList.contains('active') ? '▼' : '▶';
        });
    });

    // Back to top button
    const backToTop = document.querySelector('.back-to-top');
    window.addEventListener('scroll', () => {
        if (window.pageYOffset > 100) {
            backToTop.classList.add('visible');
        } else {
            backToTop.classList.remove('visible');
        }
    });

    backToTop.addEventListener('click', (e) => {
        e.preventDefault();
        window.scrollTo({ top: 0, behavior: 'smooth' });
    });
});
</script>

<img src="img/MillionLLMs_vanGogh_style.webp" alt="Million LLMs Track Illustration" class="hero-image" />

# Million LLMs Track

<div class="collapse-section">
    <div class="collapse-header">
        <h2>Overview</h2>
        <span class="arrow">▶</span>
    </div>
    <div class="collapse-content">
        In the era of Large Language Models (LLMs), we envision a transformation in how information is served to users. Imagine a world where:

        - Content providers like Wikipedia, NY Times, Reddit, and Elsevier offer information through specialized LLMs
        - Some LLMs provide cited responses with original source materials, while others offer direct answers
        - Different levels of cooperation exist among LLMs, from those sharing embeddings and internal weights to those providing only text outputs
        - Various access models coexist, from free-to-query to cost-based services
        - Millions of LLMs operate with distinct, sometimes overlapping expertise domains
    </div>
</div>

<div class="collapse-section">
    <div class="collapse-header">
        <h2>Research Context</h2>
        <span class="arrow">▶</span>
    </div>
    <div class="collapse-content">
        The challenge bears similarities to established fields such as:
        - Distributed Information Retrieval (DIR)
        - Federated Search (FS)
        - Meta-search

        A key distinction lies in the nature of collecting statistics: while traditional search engines return thousands of results enabling reliable statistics, LLM responses are typically brief, making expertise assessment more challenging.
    </div>
</div>

<div class="collapse-section">
    <div class="collapse-header">
        <h2>Key Challenges</h2>
        <span class="arrow">▶</span>
    </div>
    <div class="collapse-content">
        <h3>1. Evaluation Framework Development</h3>
        While we propose a specific simulation and evaluation framework, our assumptions may not fully reflect real-world conditions. Bridging this gap and developing more accurate evaluation methodologies remains a crucial challenge.

        <h3>2. LLM Expertise Quantification</h3>
        Unlike traditional DIR systems where search engines provide extensive results, LLMs typically respond with concise answers, sometimes with limited references. This brevity complicates the assessment of LLM expertise.

        <h3>3. LLM Ranking Optimization</h3>
        Even with robust expertise assessment, determining optimal LLM ranking strategies for meta-LLM agents remains complex. While this year's track focuses primarily on LLM ranking, future iterations may explore this challenge further.

        <h3>4. Answer Synthesis</h3>
        The challenge of effectively combining multiple LLM responses into coherent, comprehensive answers represents an open research question with limited existing work.
    </div>
</div>

<div class="collapse-section">
    <div class="collapse-header">
        <h2>Track Objectives</h2>
        <span class="arrow">▶</span>
    </div>
    <div class="collapse-content">
        We invite the Information Retrieval community to:
        1. Explore methods for selective LLM querying
        2. Develop robust evaluation frameworks
        3. Build a collaborative research community around these challenges
    </div>
</div>

## Organizers

<table class="organizers-table">
  <tr>
    <td>
      <img src="img/kanoulas.jpeg" alt="Evangelos Kanoulas">
      <div class="name">Evangelos Kanoulas</div>
      <div class="affiliation">University of Amsterdam, The Netherlands</div>
    </td>
    <td>
      <img src="img/eustratiadis.jpeg" alt="Panagiotis Eustratiadis">
      <div class="name">Panagiotis Eustratiadis</div>
      <div class="affiliation">University of Amsterdam, The Netherlands</div>
    </td>
    <td>
      <img src="img/sanderson.jpeg" alt="Mark Sanderson">
      <div class="name">Mark Sanderson</div>
      <div class="affiliation">RMIT University, Australia</div>
    </td>
    <td>
      <img src="img/callan.jpeg" alt="Jamie Callan">
      <div class="name">Jamie Callan</div>
      <div class="affiliation">Carnegie Mellon University, USA</div>
    </td>
  </tr>
</table>

<a href="#" class="back-to-top">↑</a>
