<script setup>
import { ref } from 'vue'


const programs = ref([
  {
    id: 'bsit',
    code: 'BSIT',
    title: 'Bachelor of Science in Information Technology (BSIT)',
    description: 'The Information Technology (IT) program is designed to bridge the gap between computer science and management information systems.',

    logo: '/src/assets/IT.png', 
    color: '#38006b'
  },
  {
    id: 'bscs',
    code: 'BSCS',
    title: 'Bachelor of Science in Computer Science (BSCS)',
    description: 'The Computer Science (CS) Program is designed for students who wants to study computing in depth, focusing in the software, the hardware',

    logo: '/src/assets/CCS.png',
    color: '#53127d'
  },
  {
    id: 'bsdmia',
    code: 'BSDMIA',
    title: 'BS in Digital Media and Interactive Arts (BSDMIA)',
    description: 'The Degree of Bachelor of Science in Digital Media and Interactive Arts is focused on creativity, applied arts and digital media technologies.',
  
    logo: '/src/assets/MEDIA.png',
    color: '#c39e18'
  },
  {
    id: 'blis',
    code: 'BLIS',
    title: 'Bachelor of Library and Information Science (BLIS)',
    description: 'The Degree of Bachelor of Library and Information Science (BLIS) is a four-year program that prepares students in the development',

    logo: '/src/assets/BLIS.png', 
    color: '#7a1fa2'
  }
])
</script>

<template>
  <section id="programs" class="programs-section">
    <div class="section-container">
      <div class="section-header">
        <p class="section-eyebrow">Academic Offerings</p>
        <h2 class="section-title">Programs Offered</h2>
        <div class="header-line"></div>
        <p class="section-subtitle">
          Empowering future technology leaders through industry-aligned computing education and world-class curricula.
        </p>
      </div>

      <div class="programs-grid">
        <div v-for="prog in programs" :key="prog.id" class="program-card">

          <div class="program-logo-container">
            <img
              v-if="prog.logo"
              :src="prog.logo"
              :alt="prog.title"
              class="program-logo"
            />
            <div v-else class="program-logo-placeholder" :style="{ borderColor: prog.color }">
              <span class="placeholder-code" :style="{ color: prog.color }">{{ prog.code }}</span>
              <span class="placeholder-sub">150 × 150</span>
            </div>
          </div>


          <h3 class="program-title">{{ prog.title }}</h3>


          <p class="program-desc">{{ prog.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.programs-section {
  width: 100%;
  padding: 4rem 2rem;
  background-color: #ffffff;
}

.section-container {
  max-width: 1200px;
  margin: 0 auto;
}

.section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-eyebrow {
  color: hsl(51, 78%, 43%);
  font-size: 16px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-family: 'Gill Sans MT', sans-serif;
  margin-bottom: 0.25rem;
}

.section-title {
  color: hsl(276, 100%, 21%);
  font-size: 38px;
  font-weight: 700;
  font-family: Arial, sans-serif;
  margin: 0;
}

.header-line {
  width: 60px;
  height: 3px;
  background-color: hsl(51, 78%, 43%);
  margin: 0.75rem auto 1rem auto;
  border-radius: 2px;
}

.section-subtitle {
  color: #5f6368;
  font-size: 16px;
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.5;
  font-family: 'Gill Sans MT', sans-serif;
}


.programs-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2rem;
}

.program-card {
  background-color: #ffffff;
  border: 1px solid #e2e8f0;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
  padding: 2.5rem 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.program-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 25px rgba(56, 0, 107, 0.1);
  border-color: #cbd5e1;
}


.program-logo-container {
  width: 150px;
  height: 150px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
  flex-shrink: 0;
}

.program-logo {
  width: 150px;
  height: 150px;
  object-fit: contain;
}

.program-logo-placeholder {
  width: 150px;
  height: 150px;
  border: 2px dashed #cbd5e1;
  border-radius: 12px;
  background-color: #f8fafc;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 4px;
}

.placeholder-code {
  font-size: 26px;
  font-weight: 800;
  letter-spacing: 1px;
  font-family: Arial, sans-serif;
}

.placeholder-sub {
  font-size: 12px;
  color: #94a3b8;
  font-weight: 600;
}


.program-title {
  color: hsl(276, 100%, 21%);
  font-size: 22px;
  font-weight: 700;
  font-family: Arial, sans-serif;
  margin: 0 0 1rem 0;
  line-height: 1.3;
}


.program-desc {
  color: #4b5563;
  font-size: 15px;
  line-height: 1.6;
  margin: 0;
  font-family: Arial, sans-serif;
}

@media (max-width: 900px) {
  .programs-grid {
    grid-template-columns: 1fr;
  }
  .section-title {
    font-size: 30px;
  }
}
</style>
