<template>
  <header class="site-header">
    <div class="brand">
      <a href="#top" class="brand-name">Melina Yorgova</a>
      <p class="brand-role">Développeuse web full-stack en formation</p>
    </div>

    <nav class="nav-menu">
      <a href="#presentation">Présentation</a>
      <a href="#creations">Créations</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
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

.brand {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.brand-name {
  text-decoration: none;
  color: #1f1f1f;
  font-size: 1.35rem;
  font-weight: 700;
  letter-spacing: 0.02em;
}

.brand-role {
  font-size: 0.85rem;
  color: #7c6f62;
  margin: 0;
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
  content: '';
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

.nav-menu a:hover {
  color: #8b6f52;
}

.nav-menu a:hover::after {
  transform: scaleX(1);
}

@media (max-width: 900px) {
  .site-header {
    flex-direction: column;
    gap: 16px;
    padding: 20px 24px;
  }

  .brand {
    align-items: center;
    text-align: center;
  }

  .nav-menu {
    gap: 18px;
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>
