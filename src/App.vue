<script setup>
import { ref } from 'vue';
import Projects from './components/Projects.vue';
import Experience from './components/Experience.vue';

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>

<template>
  <div class="app-container">
    <!-- Navigation Bar -->
    <nav class="navbar">
      <div class="container">
        <div class="logo">
          <div class="logo-image">
            <img src="./assets/CORE.jpg" alt="PRIMORDIAL CORE Logo">
          </div>
          <span>PRIMORDIAL&nbsp;</span>
        </div>
        <div class="hamburger" @click="toggleMenu">
          <div class="bar"></div>
          <div class="bar"></div>
          <div class="bar"></div>
        </div>
        <div class="nav-links" :class="{ 'active': isMenuOpen }">
          <a href="#home" @click="toggleMenu">Home</a>
          <a href="#about" @click="toggleMenu">About</a>
          <a href="#skills" @click="toggleMenu">Skills</a>
          <a href="#projects" @click="toggleMenu">Projects</a>
          <a href="#experience" @click="toggleMenu">Experience</a>
          <a href="#contact" @click="toggleMenu">Contact</a>
        </div>
      </div>
    </nav>

    <!-- Main Content -->
    <main>
      <!-- Hero Section -->
      <section id="home" class="hero-section">
        <div class="hero-content">
          <h1>IFEOLUWA CHUKWUEMEKA OWORU</h1>
          <h2>PRIMORDIAL</h2>
          <p>Full Stack Web Developer</p>
          <div class="cta-buttons">
            <a href="#contact" class="btn primary-btn">Contact Me</a>
            <a href="#projects" class="btn secondary-btn">View Projects</a>
          </div>
        </div>
      </section>

      <!-- About Section -->
      <section id="about" class="about-section">
        <h2 class="section-title">About Me</h2>
        <div class="about-content">
          <div class="profile-image-container">
            <img src="./assets/me.jpg" alt="Ifeoluwa Chukwuemeka Oworu" class="profile-image">
          </div>
          <div class="about-text">
            <p>I'm a passionate and curious Full Stack Web Developer who enjoys building things that live on the internet. With hands-on experience using HTML, CSS, JavaScript, Vue.js, Node.js, MySQL, and other modern web technologies, I thrive on crafting clean, efficient, and user-friendly solutions.</p>
            <!-- <p>I'm also deeply interested in Machine Learning, often exploring projects with Python, Pandas, and Matplotlib to bring data to life. Whether it's frontend creativity or backend logic, I'm always eager to learn, collaborate, and contribute meaningfully to any tech-forward team.</p> -->
          </div>
        </div>
      </section>

      <!-- Skills Section -->
      <section id="skills" class="skills-section">
        <h2 class="section-title">Skills</h2>
        <div class="skills-container">
          <div class="skill-category">
            <h3>Web Development</h3>
            <div class="skill-items">
              <div class="skill-item">HTML</div>
              <div class="skill-item">CSS</div>
              <div class="skill-item">Bootstrap</div>
              <div class="skill-item">JavaScript</div>
              <div class="skill-item">Vue.js</div>
              <div class="skill-item">Node.js</div>
              <div class="skill-item">MySQL</div>
              <div class="skill-item">MongoDB</div>
            </div>
          </div>
          <!--
          <div class="skill-category">
            <h3>Machine Learning & Data</h3>
            <div class="skill-items">
              <div class="skill-item">Python</div>
              <div class="skill-item">Pandas</div>
              <div class="skill-item">Matplotlib</div>
              <div class="skill-item">Data Visualization</div>
            </div>
          </div>
          -->
          <div class="skill-category">
            <h3>Tools & Others</h3>
            <div class="skill-items">
              <div class="skill-item">Git & GitHub</div>
              <div class="skill-item">Vercel</div>
              <div class="skill-item">VS Code</div>
              <div class="skill-item">Communication</div>
              <div class="skill-item">Problem-Solving</div>
              <div class="skill-item">Teamwork</div>
            </div>
          </div>
        </div>
      </section>

      <!-- Projects Section -->
      <section id="projects" class="projects-section">
        <h2 class="section-title">Projects</h2>
        <Projects />
      </section>

      <!-- Experience Section -->
      <section id="experience" class="experience-section">
        <h2 class="section-title">Experience & Education</h2>
        <Experience />
      </section>

      <!-- Contact Section -->
      <section id="contact" class="contact-section">
        <h2 class="section-title">Contact Me</h2>
        <div class="contact-content">
          <div class="contact-info">
            <div class="contact-item">
              <i class="bi bi-envelope-fill"></i>
              <p>ifeoluwaoworu@gmail.com</p>
            </div>
            <div class="contact-item">
              <i class="bi bi-telephone-fill"></i>
              <p>+234-814-166-5766 | +234-701-539-1099</p>
            </div>
          </div>
          <div class="social-links">
            <a href="https://github.com/ifelouwa" target="_blank" class="social-link"><i class="bi bi-github"></i></a>
            <a href="https://www.linkedin.com/in/ifeoluwa-oworu-933b7735a/" target="_blank" class="social-link"><i class="bi bi-linkedin"></i></a>
            <a href="https://x.com/LOVEPRIMORDIAL?t=5iOgLQRRNlFYkyOKSmGI-g&s=09" target="_blank" class="social-link"><i class="bi bi-twitter-x"></i></a>
            <a href="https://discord.com/channels/love_primordial" target="_blank" class="social-link"><i class="bi bi-discord"></i></a>
          </div>
        </div>
      </section>
    </main>

    <!-- Footer -->
    <footer>
      <p>&copy; 2024 Primordial Core. All rights reserved.</p>
      <p>Website developed by PRIMORDIAL</p>
    </footer>
  </div>
</template>

<style>
@import 'bootstrap-icons/font/bootstrap-icons.css';

:root {
  --primary-color: #7928ca;
  --secondary-color: #00d4ff;
  --dark-bg: #0a0a0a;
  --darker-bg: #050505;
  --light-text: #f0f0f0;
  --gray-text: #a0a0a0;
  --card-bg: #111111;
  --nav-bg: rgba(10, 10, 10, 0.9);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  scroll-behavior: smooth;
  overflow-x: hidden;
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Inter', 'Segoe UI', sans-serif;
  background-color: var(--dark-bg);
  color: var(--light-text);
  line-height: 1.6;
  position: relative;
}

.app-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* Navigation Styles */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: var(--nav-bg);
  backdrop-filter: blur(10px);
  z-index: 1000;
  transition: all 0.3s ease;
  padding: 1rem 0;
  margin: 0;
  border-bottom: 1px solid rgba(121, 40, 202, 0.2);
}

.navbar .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 90%;
  max-width: 1400px;
  margin: 0 auto;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
}

.logo-image {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  overflow: hidden;
}

.logo-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.logo span {
  font-size: 1.5rem;
  font-weight: 700;
  background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  letter-spacing: 1px;
}

.hamburger {
  display: none;
  cursor: pointer;
}

.bar {
  width: 25px;
  height: 3px;
  background-color: var(--light-text);
  margin: 5px 0;
  transition: all 0.3s ease;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-links a {
  color: var(--light-text);
  text-decoration: none;
  font-size: 1rem;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
}

.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
  transition: width 0.3s ease;
}

.nav-links a:hover::after {
  width: 100%;
}

/* Main Content Styles */
main {
  flex: 1;
  padding-top: 50px; /* Further reduced padding to eliminate white space */
  margin-top: 0;
  overflow-x: hidden;
}

section {
  padding: 2rem 2rem 5rem;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-top: 0;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 3rem;
  text-align: center;
  position: relative;
  display: inline-block;
  align-self: center;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 50px;
  height: 3px;
  background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
}

/* Hero Section */
.hero-section {
  background-color: var(--darker-bg);
  position: relative;
  overflow: hidden;
  padding-top: 0;
  margin-top: -55px; /* Negative margin to eliminate any remaining whitespace */
}

.hero-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at top right, rgba(121, 40, 202, 0.1), transparent 50%);
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
  z-index: 1;
  position: relative;
}

.hero-content h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-weight: 800;
}

.hero-content h2 {
  font-size: 2rem;
  margin-bottom: 1.5rem;
  color: var(--light-text);
}

.hero-content p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  color: var(--gray-text);
}

.cta-buttons {
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.btn {
  padding: 0.8rem 1.5rem;
  border-radius: 5px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
}

.primary-btn {
  background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
  color: white;
}

.secondary-btn {
  background-color: transparent;
  border: 2px solid var(--secondary-color);
  color: var(--secondary-color);
}

.primary-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.secondary-btn:hover {
  background-color: rgba(0, 212, 255, 0.1);
  transform: translateY(-3px);
}

/* About Section */
.about-section {
  background-color: var(--dark-bg);
}

.about-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 900px;
  margin: 0 auto;
  gap: 2rem;
}

.profile-image-container {
  width: 250px;
  height: 250px;
  border-radius: 50%;
  overflow: hidden;
  border: 3px solid var(--primary-color);
  box-shadow: 0 0 20px rgba(121, 40, 202, 0.3);
  margin-bottom: 2rem;
}

.profile-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.profile-image:hover {
  transform: scale(1.05);
}

.about-text p {
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
  color: var(--gray-text);
  text-align: center;
}

/* Skills Section */
.skills-section {
  background-color: var(--darker-bg);
}

.skills-container {
  display: flex;
  flex-direction: column;
  gap: 3rem;
  max-width: 1000px;
  margin: 0 auto;
}

.skill-category h3 {
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
  color: var(--light-text);
  text-align: center;
}

.skill-items {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
}

.skill-item {
  background-color: var(--card-bg);
  padding: 0.8rem 1.5rem;
  border-radius: 5px;
  font-size: 1rem;
  color: var(--light-text);
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
}

.skill-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  border-color: var(--primary-color);
}

/* Projects Section */
.projects-section {
  background-color: var(--dark-bg);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

/* Experience Section */
.experience-section {
  background-color: var(--darker-bg);
}

.timeline {
  max-width: 800px;
  margin: 0 auto;
}

/* Contact Section */
.contact-section {
  background-color: var(--dark-bg);
}

.contact-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3rem;
  max-width: 800px;
  margin: 0 auto;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.contact-item i {
  font-size: 1.5rem;
  color: var(--primary-color);
}

.social-links {
  display: flex;
  gap: 1.5rem;
  margin-top: 2rem;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: var(--card-bg);
  color: var(--light-text);
  font-size: 1.5rem;
  transition: all 0.3s ease;
  text-decoration: none;
}

.social-link:hover {
  transform: translateY(-5px);
  background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
  color: white;
}

/* Footer */
footer {
  background-color: var(--darker-bg);
  padding: 2rem;
  text-align: center;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

footer p {
  color: var(--gray-text);
  margin-bottom: 0.5rem;
}

/* Responsive Styles */
@media (max-width: 768px) {
  .navbar {
    padding: 1rem 0;
  }
  
  .navbar .container {
    width: 95%;
  }

  .hamburger {
    display: block;
  }

  .nav-links {
    position: fixed;
    top: 70px;
    left: -100%;
    width: 100%;
    height: calc(100vh - 70px);
    background-color: var(--nav-bg);
    flex-direction: column;
    align-items: center;
    justify-content: center;
    transition: all 0.5s ease;
    backdrop-filter: blur(10px);
  }

  .nav-links.active {
    left: 0;
  }

  .hero-content h1 {
    font-size: 2.5rem;
  }

  .hero-content h2 {
    font-size: 1.5rem;
  }

  .section-title {
    font-size: 2rem;
  }

  .cta-buttons {
    flex-direction: column;
    width: 100%;
    max-width: 300px;
    margin: 0 auto;
  }

  .projects-grid {
    grid-template-columns: 1fr;
  }

  .contact-content {
    gap: 2rem;
  }
}
</style>

<style scoped></style>
