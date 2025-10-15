<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'
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
import Howtops from './components/Howtops.vue'
import DownloadBlock from './components/DownloadBlock.vue'
import Sto from './components/sto.vue'
import primes from './components/primes.vue'

import Super from './components/super.vue'

import fot from './components/fot.vue'

import Footer from './components/Footer.vue'
import Abouts from './components/Abouts.vue'

import Headers from './components/Headers.vue'
import Uslugto from './components/Uslugto.vue'
import Advant from './components/Advant.vue'
import Workstep from './components/Workstep.vue'

import Test from './components/test.vue'

import Pricing from './components/pricing.vue'

const showButton = ref(true)

const scrollToContact = () => {
  const contactBlock = document.querySelector('#fot')
  if (contactBlock) {
    contactBlock.scrollIntoView({ behavior: 'smooth' })
  }
}

const handleScroll = () => {
  const fotBlock = document.querySelector('#fot')
  if (!fotBlock) return

  const rect = fotBlock.getBoundingClientRect()
  showButton.value = rect.top > window.innerHeight
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})


</script>

<template>

  <div class="common-layout">
    <el-container>

      <!-- <Headers/> -->
      <Menuv/>
<!-- 
      <Test/> -->
      <el-main>

 
        <Uslugy/>
        <!-- <Uslugto/> -->
        
        <!-- <Abouts/> -->
        <About/>
     
        <!-- <Advant/>
        <Workstep/>
        <Prime/> -->
        <HowWorks/>
        <Howtops/>
          <primes/>
        <Sto/>
       <Pricing/>
        <!-- <Super/> -->
        <!-- <DownloadBlock/> -->
        <CTA/>
        <!-- <fot/> -->


  <button
    v-show="showButton"
    class="contact-button"
    @click="scrollToContact"
  >
    связаться
  </button>

      </el-main>

      <el-footer style="padding: 0">
        <Footer/>
      </el-footer>

    </el-container>
  </div>
</template>



<style scoped>




.contact-button {
  position: fixed;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
 background-color: #0d72b9;
  color: white;
  font-size: 18px;
  padding: 14px 32px;
  border-radius: 40px;
  border: none;
  z-index: 999;
  width: 75%;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
}

@media (min-width: 769px) {
  .contact-button {
    display: none;
  }
}


.el-main{
  padding: 0;
}
/* @media (max-width: 768px) {
  .el-footer{
    display: none;
  }
} */
</style>


