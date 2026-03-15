<template>
  <footer class="site-footer">
    <div class="footer-top">
      <div class="footer-brand">
        <h3>Melina Yorgova</h3>
        <p>Portfolio de développement web</p>
      </div>

      <div class="footer-links">
        <a href="https://github.com/" target="_blank" rel="noopener noreferrer">GitHub</a>
        <a href="https://www.linkedin.com/" target="_blank" rel="noopener noreferrer">LinkedIn</a>
        <a href="#contact">Contact</a>
      </div>
    </div>

    <div class="footer-bottom">
      <p>Dernière mise à jour : mars 2026</p>
      <p>Conçu avec Vue.js, HTML, CSS et JavaScript.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
}
</script>

<style scoped>
.site-footer {
  margin-top: 80px;
  padding: 48px 56px 32px;
  background: #1f1c19;
  color: #f4eee8;
}

.footer-top {
  display: flex;
  justify-content: space-between;
  gap: 30px;
  align-items: flex-start;
  padding-bottom: 26px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.12);
}

.footer-brand h3 {
  margin: 0 0 10px;
  font-size: 1.35rem;
}

.footer-brand p {
  margin: 0;
  color: #d7ccc0;
}

.footer-links {
  display: flex;
  gap: 22px;
  flex-wrap: wrap;
}

.footer-links a {
  text-decoration: none;
  color: #f4eee8;
  transition: color 0.2s ease;
}

.footer-links a:hover {
  color: #c7a98a;
}

.footer-bottom {
  padding-top: 20px;
  display: flex;
  justify-content: space-between;
  gap: 20px;
  flex-wrap: wrap;
  color: #cdbfb2;
  font-size: 0.95rem;
}

.footer-bottom p {
  margin: 0;
}

@media (max-width: 900px) {
  .site-footer {
    padding: 40px 24px 28px;
  }

  .footer-top,
  .footer-bottom {
    flex-direction: column;
  }
}
</style>
