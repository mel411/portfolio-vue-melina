<template>
  <div class="modal-overlay" @click.self="$emit('close')">
    <div class="modal">
      <button class="close-btn" @click="$emit('close')">×</button>

      <p class="modal-label">Détail du projet</p>
      <h2>{{ title }}</h2>

      <div class="modal-meta">
        <p><strong>Date :</strong> {{ date }}</p>
        <p><strong>Technologies :</strong> {{ tech }}</p>
      </div>

      <p class="description">
        {{ description }}
      </p>

      <div class="modal-links">
        <a
          v-if="demo && demo !== '#'"
          :href="demo"
          target="_blank"
          rel="noopener noreferrer"
        >
          Voir le projet
        </a>

        <a
          v-if="github && github !== '#'"
          :href="github"
          target="_blank"
          rel="noopener noreferrer"
        >
          Voir le GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectModal',
  props: {
    title: String,
    date: String,
    tech: String,
    description: String,
    demo: String,
    github: String,
  },
  emits: ['close'],
}
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(18, 16, 14, 0.56);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 3000;
  padding: 20px;
}

.modal {
  position: relative;
  width: 100%;
  max-width: 650px;
  background: #fcfaf7;
  border: 1px solid #e5ddd2;
  border-radius: 22px;
  padding: 38px 34px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.14);
}

.close-btn {
  position: absolute;
  top: 14px;
  right: 16px;
  border: none;
  background: transparent;
  font-size: 30px;
  cursor: pointer;
  color: #4c4034;
}

.modal-label {
  margin: 0 0 10px;
  color: #8b6f52;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  font-size: 0.78rem;
  font-weight: 700;
}

.modal h2 {
  margin: 0 0 22px;
  font-size: 2rem;
  line-height: 1.2;
  color: #1f1f1f;
}

.modal-meta {
  display: grid;
  gap: 8px;
  margin-bottom: 20px;
}

.modal-meta p,
.description {
  color: #41372f;
  line-height: 1.7;
}

.description {
  margin: 0 0 24px;
}

.modal-links {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
}

.modal-links a {
  text-decoration: none;
  background: #1f1c19;
  color: #fff;
  padding: 12px 18px;
  border-radius: 999px;
  font-weight: 600;
  transition:
    background 0.2s ease,
    transform 0.2s ease;
}

.modal-links a:last-child {
  background: #8b6f52;
}

.modal-links a:hover {
  transform: translateY(-1px);
}
</style>
