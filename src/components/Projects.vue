<script setup>
import { ref } from 'vue';
import ProjectCard from './ProjectCard.vue';

const projects = ref([
  {
    title: 'Quiz App',
    description: 'Interactive quiz application with multiple categories and difficulty levels.',
    githubLink: 'https://github.com/ifelouwa/Quiz-App',
    liveLink: 'https://quiz-app-three-dusky.vercel.app/',
    technologies: ['HTML', 'CSS', 'JavaScript']
  },
  {
    title: 'Fake News Classifier',
    description: 'NLP-based machine learning project that detects and classifies fake news articles using text analysis.',
    githubLink: 'https://github.com/ifelouwa/fruit-classifier',
    liveLink: '',
    technologies: ['Python', 'Pandas', 'NumPy']
  },
  {
    title: 'UNISCA',
    description: 'Frontend perfume store website using HTML, CSS.',
    githubLink: 'https://github.com/ifelouwa/Fragrance',
    liveLink: '',
    technologies: ['HTML', 'CSS']
  },
  {
    title: 'Waterloo University',
    description: 'Frontend clone of a prestigious university website.',
    githubLink: 'https://github.com/ifelouwa/Waterloo',
    liveLink: '',
    technologies: ['HTML', 'CSS']
  },
  {
    title: 'Calculator',
    description: 'A functional calculator application with a clean interface.',
    githubLink: 'https://github.com/yourusername/calculator',
    liveLink: '',
    technologies: ['JavaScript', 'HTML', 'CSS']
  },
  {
    title: 'Weather App',
    description: 'Dynamic weather web application that provides real-time weather information.',
    githubLink: 'https://github.com/yourusername/weather-app',
    liveLink: '',
    technologies: ['JavaScript', 'API', 'HTML', 'CSS']
  },
  {
    title: 'Fruit Classifier',
    description: 'Machine learning model that classifies different types of fruits from images with high accuracy.',
    githubLink: 'https://github.com/ifelouwa/fruit-classifier',
    liveLink: '',
    technologies: ['Python', 'Matplotlib', 'Pandas']
  },
  {
    title: 'Recipe App',
    description: 'Simple web recipe application for storing and sharing favorite recipes.',
    githubLink: 'https://github.com/ifelouwa/Food-stall',
    liveLink: '',
    technologies: ['JavaScript', 'HTML', 'CSS']
  },
  {
    title: 'Note-Taking App',
    description: 'Basic note-taking application for creating, editing, and organizing notes.',
    githubLink: 'https://github.com/yourusername/note-app',
    liveLink: '',
    technologies: ['JavaScript', 'HTML', 'CSS']
  }
]);
</script>

<template>
  <div class="projects-grid">
    <ProjectCard 
      v-for="(project, index) in projects" 
      :key="index"
      :title="project.title"
      :description="project.description"
      :githubLink="project.githubLink"
      :liveLink="project.liveLink"
      :technologies="project.technologies"
    />
  </div>
</template>

<style scoped>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>