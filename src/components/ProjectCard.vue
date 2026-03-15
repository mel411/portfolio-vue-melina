<template>
  <article class="project-card" @click="$emit('open')">
    <div class="image-wrapper">
      <img :src="image" :alt="title" />
      <div class="image-overlay">
        <span>Voir le projet</span>
      </div>
    </div>

    <div class="project-content">
      <p class="project-tag">{{ tag }}</p>
      <h3>{{ title }}</h3>
    </div>
  </article>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    title: String,
    image: String,
    tag: String,
  },
  emits: ['open'],
}
</script>

<style scoped>
.project-card {
  cursor: pointer;
  background: #ffffff;
  border: 1px solid #e9dfd3;
  border-radius: 18px;
  overflow: hidden;
  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease;
}

.project-card:hover {
  transform: translateY(-6px) scale(1.01);
  box-shadow: 0 18px 40px rgba(0, 0, 0, 0.08);
}

.image-wrapper {
  position: relative;
  overflow: hidden;
}

.project-card img {
  width: 100%;
  height: 260px;
  object-fit: cover;
  display: block;
  transition: transform 0.35s ease;
}

.project-card:hover img {
  transform: scale(1.04);
}

.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(31, 28, 25, 0.72), rgba(31, 28, 25, 0.08));
  display: flex;
  align-items: flex-end;
  justify-content: flex-start;
  padding: 20px;
  opacity: 0;
  transition: opacity 0.25s ease;
}

.project-card:hover .image-overlay {
  opacity: 1;
}

.image-overlay span {
  color: #fff;
  font-size: 0.92rem;
  letter-spacing: 0.03em;
}

.project-content {
  padding: 20px 20px 24px;
  text-align: left;
}

.project-tag {
  margin: 0 0 10px;
  font-size: 0.78rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #8b6f52;
  font-weight: 700;
}

.project-content h3 {
  margin: 0;
  font-size: 1.2rem;
  line-height: 1.35;
  color: #1f1f1f;
  letter-spacing: -0.01em;
}
</style>
