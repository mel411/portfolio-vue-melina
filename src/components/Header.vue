<template>
  <header class="site-header">
    <a href="#top" class="brand-link" aria-label="Retour en haut de la page">
      <div class="logo-mark">MY</div>
      <div class="brand-text">
        <span class="brand-name">Melina Yorgova</span>
        <span class="brand-role">Développeuse web full-stack en formation</span>
      </div>
    </a>

    <nav class="nav-menu" aria-label="Navigation principale">
      <a
        href="#presentation"
        :class="{ active: activeSection === 'presentation' }"
      >
        Présentation
      </a>

      <a
        href="#creations"
        :class="{ active: activeSection === 'creations' }"
      >
        Créations
      </a>

      <a
        href="#contact"
        :class="{ active: activeSection === 'contact' }"
      >
        Contact
      </a>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {
    activeSection: {
      type: String,
      default: "",
    },
  },
};
</script>

<style scoped>
.site-header {
  position: sticky;
  top: 0;
  z-index: 1000;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 22px 56px;
  background: rgba(248, 245, 240, 0.92);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid #e5ddd2;
}

.brand-link {
  display: flex;
  align-items: center;
  gap: 14px;
  text-decoration: none;
}

.logo-mark {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  background: #1f1c19;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.95rem;
  font-weight: 700;
  letter-spacing: 0.08em;
}

.brand-text {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.brand-name {
  color: #1f1f1f;
  font-size: 1.35rem;
  font-weight: 700;
  letter-spacing: 0.02em;
}

.brand-role {
  font-size: 0.85rem;
  color: #7c6f62;
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 28px;
}

.nav-menu a {
  position: relative;
  text-decoration: none;
  color: #2b2b2b;
  font-size: 0.98rem;
  font-weight: 500;
  transition: color 0.2s ease;
}

.nav-menu a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -7px;
  width: 100%;
  height: 1.5px;
  background: #8b6f52;
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.25s ease;
}

.nav-menu a:hover,
.nav-menu a.active {
  color: #8b6f52;
}

.nav-menu a.active::after,
.nav-menu a:hover::after {
  transform: scaleX(1);
}

@media (max-width: 900px) {
  .site-header {
    flex-direction: column;
    gap: 16px;
    padding: 20px 24px;
  }

  .brand-text {
    text-align: center;
  }

  .nav-menu {
    gap: 18px;
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>