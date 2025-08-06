<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  period: {
    type: String,
    required: true
  },
  organization: {
    type: String,
    required: true
  },
  location: {
    type: String,
    default: ''
  },
  description: {
    type: String,
    default: ''
  },
  points: {
    type: Array,
    default: () => []
  },
  isLeft: {
    type: Boolean,
    default: true
  }
});
</script>

<template>
  <div class="timeline-item" :class="{ 'left': isLeft, 'right': !isLeft }">
    <div class="timeline-content">
      <div class="timeline-date">{{ period }}</div>
      <h3 class="timeline-title">{{ title }}</h3>
      <div class="timeline-org">{{ organization }} <span v-if="location">| {{ location }}</span></div>
      <p v-if="description" class="timeline-description">{{ description }}</p>
      <ul v-if="points.length > 0" class="timeline-points">
        <li v-for="(point, index) in points" :key="index">{{ point }}</li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.timeline-item {
  position: relative;
  margin-bottom: 3rem;
  width: 100%;
}

.timeline-item::before {
  content: '';
  position: absolute;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
  top: 0;
}

.timeline-item::after {
  content: '';
  position: absolute;
  width: 2px;
  height: calc(100% + 3rem);
  background-color: rgba(255, 255, 255, 0.1);
  top: 0;
}

.timeline-item.left::before {
  left: -8px;
}

.timeline-item.right::before {
  right: -8px;
}

.timeline-item.left::after {
  left: 0;
}

.timeline-item.right::after {
  right: 0;
}

.timeline-content {
  background-color: var(--card-bg);
  border-radius: 10px;
  padding: 1.5rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
}

.timeline-item.left .timeline-content {
  margin-left: 2rem;
}

.timeline-item.right .timeline-content {
  margin-right: 2rem;
  text-align: right;
}

.timeline-content:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  border-color: var(--primary-color);
}

.timeline-date {
  display: inline-block;
  padding: 0.3rem 0.8rem;
  background-color: rgba(121, 40, 202, 0.2);
  color: var(--light-text);
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 500;
  margin-bottom: 0.8rem;
}

.timeline-title {
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
  color: var(--light-text);
}

.timeline-org {
  color: var(--secondary-color);
  font-size: 1rem;
  margin-bottom: 1rem;
}

.timeline-description {
  color: var(--gray-text);
  margin-bottom: 1rem;
}

.timeline-points {
  padding-left: 1.5rem;
  color: var(--gray-text);
}

.timeline-item.right .timeline-points {
  padding-left: 0;
  padding-right: 1.5rem;
  list-style-position: inside;
}

.timeline-points li {
  margin-bottom: 0.5rem;
}

@media (max-width: 768px) {
  .timeline-item.left::before,
  .timeline-item.right::before {
    left: -8px;
  }
  
  .timeline-item.left::after,
  .timeline-item.right::after {
    left: 0;
  }
  
  .timeline-item.left .timeline-content,
  .timeline-item.right .timeline-content {
    margin-left: 2rem;
    margin-right: 0;
    text-align: left;
  }
  
  .timeline-item.right .timeline-points {
    padding-left: 1.5rem;
    padding-right: 0;
    list-style-position: outside;
  }
}
</style>