<script setup lang="ts">
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import 'swiper/swiper-bundle.css'


import Uslugi from './components/Uslugi.vue'
import Uslugy from './components/Uslugi.vue'
import Menu from './components/Menu.vue'
import About from './components/about.vue'
import Prime from './components/prime.vue'
import HowWorks from './components/HowWorks.vue'
import CTA from './components/CTA.vue'
import Map from './components/map.vue'
import Menuv from './components/Menuv.vue'
import Howtop from './components/Howtop.vue'
import DownloadBlock from './components/DownloadBlock.vue'


import Footer from './components/Footer.vue'
</script>

<template>

  <div class="common-layout">
    <el-container>
<!--      <Menu/>-->

      <Menuv/>
      <el-main>



        <Uslugy/>

        <About/>
        <Prime/>
        <HowWorks/>
     
        <Howtop/>
           <DownloadBlock/>
        <CTA/>

      </el-main>

      <el-footer style="padding: 0">
        <Footer/>
      </el-footer>

    </el-container>
  </div>
</template>


<style scoped>
.el-main{
  padding: 0;
}
</style>





<!-- <script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style> -->
