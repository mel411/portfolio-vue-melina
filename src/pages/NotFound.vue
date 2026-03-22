<template>
  <div id="top">
    <Header />

    <main class="not-found-page">
      <div class="not-found-content">
        <img
          src="/404-illustration.svg"
          alt="Illustration de page introuvable"
          class="not-found-image"
        />

        <h1>404</h1>
        <p>La page demandée est introuvable.</p>
        <a href="/" class="back-link">Retour à l’accueil</a>
      </div>
    </main>

    <Footer />
  </div>
</template>

<script>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";

export default {
  name: "NotFound",
  components: {
    Header,
    Footer,
  },
};
</script>

<style scoped>
.not-found-page {
  min-height: 70vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 60px 24px;
  background: #fcfaf7;
}

.not-found-content {
  max-width: 720px;
  text-align: center;
}

.not-found-image {
  width: 100%;
  max-width: 460px;
  margin-bottom: 30px;
}

.not-found-content h1 {
  font-size: 4rem;
  margin-bottom: 16px;
  color: #1f1f1f;
}

.not-found-content p {
  font-size: 1.1rem;
  color: #5a5148;
  margin-bottom: 22px;
}

.back-link {
  text-decoration: none;
  background: #1f1c19;
  color: #fff;
  padding: 12px 18px;
  border-radius: 999px;
  font-weight: 600;
}
</style>