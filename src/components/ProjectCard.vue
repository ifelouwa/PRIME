<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  githubLink: {
    type: String,
    default: '#'
  },
  liveLink: {
    type: String,
    default: ''
  },
  technologies: {
    type: Array,
    default: () => []
  }
});
</script>

<template>
  <div class="project-card">
    <div class="project-content">
      <h3 class="project-title">{{ title }}</h3>
      <p class="project-description">{{ description }}</p>
      
      <div class="project-tech" v-if="technologies.length > 0">
        <span v-for="(tech, index) in technologies" :key="index" class="tech-tag">{{ tech }}</span>
      </div>
      
      <div class="project-links">
        <a :href="githubLink" target="_blank" class="project-link github-link">
          <i class="bi bi-github"></i> GitHub
        </a>
        <a v-if="liveLink" :href="liveLink" target="_blank" class="project-link live-link">
          <i class="bi bi-globe"></i> Live Demo
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.project-card {
  background-color: var(--card-bg);
  border-radius: 10px;
  overflow: hidden;
  transition: all 0.3s ease;
  height: 100%;
  display: flex;
  flex-direction: column;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  border-color: var(--primary-color);
}

.project-content {
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  flex: 1;
}

.project-title {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  color: var(--light-text);
  position: relative;
  display: inline-block;
}

.project-title::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 30px;
  height: 2px;
  background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
}

.project-description {
  color: var(--gray-text);
  margin-bottom: 1.5rem;
  flex-grow: 1;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.tech-tag {
  background-color: rgba(121, 40, 202, 0.2);
  color: var(--light-text);
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 500;
}

.project-links {
  display: flex;
  gap: 1rem;
}

.project-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.9rem;
  transition: all 0.3s ease;
}

.github-link {
  color: var(--light-text);
}

.live-link {
  color: var(--secondary-color);
}

.project-link:hover {
  transform: translateY(-2px);
}

.project-link i {
  font-size: 1.1rem;
}
</style>