<template>
  <footer class="site-footer">
    <div class="footer-top">
      <div class="footer-brand">
        <h3>Melina Yorgova</h3>
        <p>Portfolio de développement web</p>
      </div>

      <div class="footer-links">
        <a
          :href="githubUrl"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="GitHub"
        >
          <svg viewBox="0 0 24 24" aria-hidden="true">
            <path
              d="M12 2C6.48 2 2 6.58 2 12.23c0 4.52 2.87 8.35 6.84 9.71.5.1.68-.22.68-.49 0-.24-.01-1.03-.01-1.87-2.78.62-3.37-1.21-3.37-1.21-.45-1.18-1.11-1.49-1.11-1.49-.9-.63.07-.62.07-.62 1 .07 1.52 1.05 1.52 1.05.88 1.56 2.31 1.11 2.87.85.09-.66.35-1.11.63-1.37-2.22-.26-4.56-1.15-4.56-5.11 0-1.13.39-2.05 1.03-2.78-.1-.26-.45-1.31.1-2.73 0 0 .84-.28 2.75 1.06A9.3 9.3 0 0 1 12 6.84c.85 0 1.71.12 2.51.36 1.91-1.34 2.75-1.06 2.75-1.06.55 1.42.2 2.47.1 2.73.64.73 1.03 1.65 1.03 2.78 0 3.97-2.35 4.84-4.59 5.1.36.32.69.95.69 1.92 0 1.39-.01 2.5-.01 2.84 0 .27.18.6.69.49A10.24 10.24 0 0 0 22 12.23C22 6.58 17.52 2 12 2Z"
            />
          </svg>
        </a>

        <a
          :href="linkedinUrl"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="LinkedIn"
        >
          <svg viewBox="0 0 24 24" aria-hidden="true">
            <path
              d="M6.94 8.5H3.56V20h3.38V8.5ZM5.25 3A1.97 1.97 0 0 0 3.25 5a2 2 0 0 0 4 0A1.97 1.97 0 0 0 5.25 3ZM20.75 12.6c0-3.2-1.71-4.69-4-4.69-1.84 0-2.66 1.03-3.12 1.75V8.5h-3.38c.04.77 0 11.5 0 11.5h3.38v-6.42c0-.34.03-.68.12-.92.27-.68.88-1.38 1.9-1.38 1.34 0 1.88 1.03 1.88 2.55V20H20.75v-7.4Z"
            />
          </svg>
        </a>
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
  name: "Footer",
  data() {
    return {
      githubUrl: import.meta.env.VITE_GITHUB_URL || "https://github.com/mel411",
      linkedinUrl: import.meta.env.VITE_LINKEDIN_URL || "https://www.linkedin.com/",
    };
  },
};
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
  gap: 18px;
  flex-wrap: wrap;
}

.footer-links a {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.08);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.2s ease, transform 0.2s ease;
}

.footer-links a:hover {
  background: rgba(199, 169, 138, 0.22);
  transform: translateY(-1px);
}

.footer-links svg {
  width: 20px;
  height: 20px;
  fill: #f4eee8;
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