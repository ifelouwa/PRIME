<script setup>
import { ref } from 'vue';
import TimelineItem from './TimelineItem.vue';

const experiences = ref([
  {
    title: 'Web Developer',
    period: '04/05/2025 – PRESENT',
    organization: 'Tai Solarin Federal University of Education',
    location: 'Ijebu-Ode',
    description: '',
    points: [
      'Developing and maintaining university web applications',
      'Implementing database solutions for student records',
      'Collaborating with IT team on system improvements'
    ],
    isLeft: true
  },
  {
    title: 'IT Staff',
    period: 'JUN 2024 – JUN 2025',
    organization: 'Lagos State University of Education (NYSC)',
    location: '',
    description: '',
    points: [
      'Provided IT support and maintenance for digital infrastructure',
      'Engaged in system troubleshooting and optimization',
      'Collaborated with colleagues on web development initiatives'
    ],
    isLeft: false
  },
  {
    title: 'Computer Science Teacher',
    period: 'JAN 2023 – JUN 2023',
    organization: 'Secondary School',
    location: 'Ijebu-Ode',
    description: '',
    points: [
      'Taught basic computer science concepts to students',
      'Developed engaging lesson plans with practical sessions'
    ],
    isLeft: false
  },
  {
    title: 'Hardware Engineering Intern',
    period: 'DEC 2021 – FEB 2022',
    organization: '',
    location: 'Ijebu-Ode',
    description: '',
    points: [
      'Supported hardware repairs and network troubleshooting',
      'Participated in hands-on tech maintenance and learning'
    ],
    isLeft: true
  }
]);

const education = ref([
  {
    title: 'B.Sc (Ed.) Computer Science',
    period: '2019 – 2023',
    organization: 'Tai Solarin University of Education',
    location: 'Ijebu-Ode',
    description: '',
    points: [],
    isLeft: false
  },
  {
    title: 'West African School Certificate',
    period: '2014 – 2019',
    organization: 'Adeola Odutola College (Private)',
    location: 'Ijebu-Ode',
    description: '',
    points: [],
    isLeft: true
  }
]);

const certificates = ref([
  {
    title: 'Leadership Certificate',
    period: 'JAN 2022',
    organization: 'Chartered Institute of Leadership and Governance (USA)',
    location: '',
    description: '',
    points: [],
    isLeft: false
  },
  {
    title: 'Backend Development (3 Months)',
    period: 'AUG 2025 - OCT 2025',
    organization: 'TECHCRUSH',
    location: '',
    description: '',
    points: [],
    isLeft: true
  },
]);
</script>

<template>
  <div class="timeline-container">
    <h3 class="timeline-section-title">Work Experience</h3>
    <div class="timeline">
      <TimelineItem 
        v-for="(exp, index) in experiences" 
        :key="'exp-' + index"
        :title="exp.title"
        :period="exp.period"
        :organization="exp.organization"
        :location="exp.location"
        :description="exp.description"
        :points="exp.points"
        :isLeft="exp.isLeft"
      />
    </div>
    
    <h3 class="timeline-section-title">Education</h3>
    <div class="timeline">
      <TimelineItem 
        v-for="(edu, index) in education" 
        :key="'edu-' + index"
        :title="edu.title"
        :period="edu.period"
        :organization="edu.organization"
        :location="edu.location"
        :description="edu.description"
        :points="edu.points"
        :isLeft="edu.isLeft"
      />
    </div>
    
    <h3 class="timeline-section-title">Certificates</h3>
    <div class="timeline">
      <TimelineItem 
        v-for="(cert, index) in certificates" 
        :key="'cert-' + index"
        :title="cert.title"
        :period="cert.period"
        :organization="cert.organization"
        :location="cert.location"
        :description="cert.description"
        :points="cert.points"
        :isLeft="cert.isLeft"
      />
    </div>
  </div>
</template>

<style scoped>
.timeline-container {
  max-width: 800px;
  margin: 0 auto;
  position: relative;
}

.timeline {
  position: relative;
  margin-bottom: 4rem;
}

.timeline::before {
  content: '';
  position: absolute;
  width: 2px;
  height: 100%;
  background-color: rgba(255, 255, 255, 0.1);
  left: 50%;
  transform: translateX(-50%);
}

.timeline-section-title {
  text-align: center;
  font-size: 1.8rem;
  margin-bottom: 2rem;
  color: var(--light-text);
  position: relative;
  display: inline-block;
  left: 50%;
  transform: translateX(-50%);
}

.timeline-section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 2px;
  background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
}

@media (max-width: 768px) {
  .timeline::before {
    left: 0;
    transform: none;
  }
}
</style>