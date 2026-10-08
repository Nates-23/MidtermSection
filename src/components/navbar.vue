<script setup>
import { useRoute, useRouter } from 'vue-router'

const route = useRoute()
const router = useRouter()

const scrollTo = (hash) => {
  if (route.path === '/') {
    const el = document.querySelector(hash)
    if (el) {
      el.scrollIntoView({ behavior: 'smooth' })
    }
  } else {
    router.push({ path: '/', hash })
  }
}
</script>

<template>
  <header id="header-container" class="body-contents-container">
    <section id="header-contents-container">
      <RouterLink to="/" class="logo-link">
        <section id="logo-title-container" class="header-contents">
          <section id="logo-container" class="header-sub-con">
            <img id="cpu-logo" src="/src/assets/CCSLogo.png" alt="CCS LOGO" width="100">
          </section>

          <section id="title-container" class="header-sub-con">
            <h1 id="school-name">College of Computer Studies</h1>
            <p id="school-quote">Knowledge Drives a Brighter Tomorrow</p>
          </section>
        </section>
      </RouterLink>

      <nav id="nav-container" class="header-contents">
        <ul id="links-container">
          <li class="links">
            <a href="#hero" class="actual-links" @click.prevent="scrollTo('#hero')">Home</a>
          </li>

          <li class="links">
            <a href="#programs" class="actual-links" @click.prevent="scrollTo('#programs')">Programs</a>
          </li>

          <li class="links">
            <a href="#faculty" class="actual-links" @click.prevent="scrollTo('#faculty')">Faculty & Staff</a>
          </li>

          <li class="links">
            <a href="#partnerships" class="actual-links" @click.prevent="scrollTo('#partnerships')">Partnerships</a>
          </li>

          <li class="links">
            <RouterLink
              to="/admissions"
              class="actual-links"
              active-class="active-link"
            >
              Admissions
            </RouterLink>
          </li>

          <a id="search-icon">
            <img src="/src/assets/search.png" width="30" alt="Search">
          </a>

          <button id="login-btn">Portal Login</button>
        </ul>
      </nav>
    </section>
  </header>
</template>

<style scoped>
#header-container {
  width: 100%;
  flex-shrink: 0;
  background-color: #ffffff;
  border-bottom: 1px solid #f1f5f9;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.08);
}

#header-contents-container {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;
}

.logo-link {
  text-decoration: none;
  display: flex;
  align-items: center;
}

.header-contents {
  height: 100%;
}

#logo-title-container,
#links-container {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

#logo-title-container {
  width: auto;
  gap: 15px;
}

#nav-container {
  width: auto;
}

#links-container {
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  gap: 20px;
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

.links {
  list-style: none;
  color: hsl(0, 0%, 31%);
  font-weight: bold;
  text-shadow: 0 0 1px hsl(0, 0%, 0%);
  font-size: 15px;
}

.actual-links {
  text-decoration: none;
  color: inherit;
  cursor: pointer;
  transition: color 0.15s ease;
  white-space: nowrap;
}

.actual-links:hover {
  color: hsl(276, 100%, 21%);
}

.active-link {
  color: hsl(276, 100%, 21%);
  font-size: 15px;
  text-decoration: underline 2px hsl(51, 100%, 36%);
  text-underline-offset: 10px;
  text-decoration-thickness: 3px;
}

.header-sub-con {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  white-space: nowrap;
}

#logo-container {
  width: auto;
}

#title-container {
  width: auto;
  align-items: flex-start;
}

#cpu-logo {
  width: 60px;
}

#school-name {
  color: hsl(276, 100%, 21%);
  text-shadow: 0 0 1px hsl(0, 0%, 0%);
  font-size: 26px;
  margin: 0;
  line-height: 1.2;
}

#school-quote {
  color: hsl(51, 100%, 36%);
  text-shadow: 0 0 1px hsl(0, 0%, 0%);
  font-family: Arial, sans-serif;
  font-size: 13px;
  margin: 0;
}

#search-icon {
  cursor: pointer;
  display: flex;
  align-items: center;
}

#login-btn {
  width: 160px;
  height: 44px;
  background-color: hsl(276, 100%, 21%);
  border-radius: 8px;
  border: none;
  color: hsl(180, 100%, 99%);
  font-size: 16px;
  font-family: Arial, sans-serif;
  font-weight: 600;
  margin-left: 10px;
  cursor: pointer;
  transition: opacity 0.2s ease;
}

#login-btn:hover {
  opacity: 0.9;
}

@media (max-width: 1024px) {
  #header-contents-container {
    flex-direction: column;
    gap: 10px;
  }
  #links-container {
    flex-wrap: wrap;
    gap: 15px;
  }
}
</style>
