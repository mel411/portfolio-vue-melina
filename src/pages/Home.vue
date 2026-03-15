<template>
  <div id="top">
    <Header />

    <main>
      <section id="presentation" class="hero-section">
        <div class="hero-shell">
          <div class="hero-copy">
            <h1>
              Je conçois des projets web
              <span>structurés, élégants et professionnels.</span>
            </h1>

            <p class="hero-text">
              Je développe des projets front-end et back-end avec une attention particulière portée
              à l’interface, à la clarté du code et à l’expérience utilisateur.
            </p>

            <div class="hero-actions">
              <a href="#creations" class="btn-primary">Voir mes projets</a>
              <a href="#contact" class="btn-secondary">Me contacter</a>
            </div>
          </div>
        </div>
      </section>

      <section id="creations" class="projects-section">
        <div class="section-head">
          <p class="section-kicker">Sélection de travaux</p>
          <h2>Mes créations</h2>
          <p class="section-subtitle">
            Une sélection de projets réalisés pendant ma formation, en développement front-end,
            back-end et full-stack.
          </p>
        </div>

        <div class="projects-grid">
          <ProjectCard
            v-for="project in projects"
            :key="project.id"
            :title="project.title"
            :image="project.image"
            :tag="project.tag"
            @open="openProject(project)"
          />
        </div>

        <ProjectModal
          v-if="showModal && selectedProject"
          :title="selectedProject.title"
          :date="selectedProject.date"
          :tech="selectedProject.tech"
          :description="selectedProject.description"
          :demo="selectedProject.demo"
          :github="selectedProject.github"
          @close="showModal = false"
        />
      </section>

      <section id="contact" class="contact-section">
        <div class="section-head">
          <p class="section-kicker">Prise de contact</p>
          <h2>Contact</h2>
          <p class="section-subtitle">
            Pour toute question relative à mon portfolio, à mes projets ou à mon parcours en
            développement web.
          </p>
        </div>

        <div class="contact-card">
          <ContactForm />
        </div>
      </section>
    </main>

    <Footer />
  </div>
</template>

<script>
import Header from '../components/Header.vue'
import Footer from '../components/Footer.vue'
import ProjectCard from '../components/ProjectCard.vue'
import ProjectModal from '../components/ProjectModal.vue'
import ContactForm from '../components/ContactForm.vue'

export default {
  name: 'Home',
  components: {
    Header,
    Footer,
    ProjectCard,
    ProjectModal,
    ContactForm,
  },
  data() {
    return {
      showModal: false,
      selectedProject: null,
      projects: [
        {
          title: 'Maquette UI/UX Figma',
          tag: 'Figma',
          image: new URL('../assets/images/figma.png', import.meta.url).href,
          date: '2026',
          tech: 'Figma, UI/UX Design',
          description:
            'Conception d’interfaces web avec Figma incluant prototypes interactifs, hiérarchie visuelle et maquettes responsives pour un projet e-commerce.',
          demo: '#',
          github: '#',
        },
        {
          title: 'CV en ligne avec React',
          tag: 'React',
          image: new URL('../assets/images/react-cv-home.png', import.meta.url).href,
          date: '2026',
          tech: 'React, JavaScript, CSS',
          description:
            'Développement d’un CV en ligne dynamique avec React, reposant sur une architecture de composants réutilisables et une interface moderne.',
          demo: '#',
          github: '#',
        },
        {
          title: 'Site dynamique avec AngularJS',
          tag: 'AngularJS',
          date: '2026',
          tech: 'AngularJS, JavaScript, HTML,CSS',
          image: new URL('../assets/images/angular.png', import.meta.url).href,
          description:
            'Réalisation d’un site dynamique avec AngularJS intégrant navigation, contenu interactif et structuration front-end orientée expérience utilisateur.',
          demo: '#',
          github: '#',
        },
        {
          title: 'API sécurisée avec Node.js',
          tag: 'Node.js',
          image: new URL('../assets/images/node-cover.png', import.meta.url).href,
          date: '2026',
          tech: 'Node.js, Express, MongoDB',
          description:
            'Développement d’une API sécurisée avec Node.js et Express incluant authentification, gestion des utilisateurs, des catways et des réservations avec MongoDB.',
          demo: '#',
          github: '#',
        },
        {
          title: 'Application e-commerce Symfony',
          tag: 'Symfony',
          image: new URL('../assets/images/symfony-cover.png', import.meta.url).href,
          date: '2026',
          tech: 'Symfony, PHP, MySQL, Twig',
          description:
            'Développement d’une application e-commerce avec Symfony incluant catalogue produits, panier, interface administrateur et gestion des utilisateurs.',
          demo: '#',
          github: '#',
        },
      ],
    }
  },
  methods: {
    openProject(project) {
      this.selectedProject = project
      this.showModal = true
    },
    closeProject() {
      this.showModal = false
      this.selectedProject = null
    },
  },
}
</script>

<style scoped>
.hero-section {
  padding: 24px 24px 72px;
  background:
    radial-gradient(circle at top left, rgba(199, 169, 138, 0.1), transparent 26%),
    linear-gradient(to bottom, #f8f5f0, #f3eee8);
}

.hero-shell {
  max-width: 1100px;
  margin: 0 auto;
  display: block;
}

.hero-copy {
  max-width: 760px;
  padding: 28px 0 0;
}

.hero-copy h1 {
  margin: 0 0 28px;
  font-size: 4.4rem;
  line-height: 1.02;
  letter-spacing: -0.04em;
  font-weight: 700;
  color: #1f1f1f;
}

.hero-copy h1 span {
  display: block;
  letter-spacing: 0em;
  font-weight: 650;
  color: #8b6f52;
}

.hero-text {
  max-width: 560px;
  font-size: 1.08rem;
  line-height: 1.85;
  color: #4a423b;
  margin: 0 0 18px;
}

.hero-actions {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
  margin-top: 34px;
}

.btn-primary,
.btn-secondary {
  text-decoration: none;
  padding: 14px 22px;
  border-radius: 999px;
  font-weight: 600;
  transition:
    transform 0.2s ease,
    background 0.2s ease;
}

.btn-primary {
  background: #1f1c19;
  color: white;
}

.btn-secondary {
  background: transparent;
  color: #1f1c19;
  border: 1px solid #bfa78d;
}

.btn-primary:hover,
.btn-secondary:hover {
  transform: translateY(-1px);
}

.projects-section,
.contact-section {
  padding: 88px 24px 0;
}

.section-head {
  max-width: 860px;
  margin: 0 auto 34px;
  text-align: center;
}

.section-kicker {
  margin: 0 0 14px;
  color: #8b6f52;
  text-transform: uppercase;
  letter-spacing: 0.09em;
  font-size: 0.8rem;
  font-weight: 700;
}

.section-head h2 {
  margin: 0 0 14px;
  font-size: 3.2rem;
  letter-spacing: -0.02em;
  color: #1f1f1f;
  line-height: 1.1;
}

.section-subtitle {
  margin: 0;
  color: #5a5148;
  font-size: 1.08rem;
  line-height: 1.8;
}

.projects-grid {
  max-width: 1180px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
}

.contact-card {
  max-width: 920px;
  margin: 0 auto;
  padding: 34px;
  border: 1px solid #eadfd4;
  border-radius: 24px;
  background: #fffdfa;
  box-shadow: 0 14px 34px rgba(90, 68, 45, 0.06);
}

@media (max-width: 1100px) {
  .hero-copy h1 {
    font-size: 3.3rem;
  }

  .projects-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 700px) {
  .hero-section {
    padding: 28px 20px 56px;
  }

  .hero-copy h1 {
    font-size: 2.5rem;
  }

  .section-head h2 {
    font-size: 2.25rem;
  }

  .projects-grid {
    grid-template-columns: 1fr;
  }

  .contact-card {
    padding: 22px;
  }
}
</style>
