<script setup lang="ts">
import { onMounted, ref, nextTick } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const stepsSection = ref(null)
const stepRefs: HTMLElement[] = []

const steps = [
  { title: 'медицинская инфраструктура', desc: '' },
  { title: 'внутренний контроль качества', desc: '' },
  { title: 'квалифицированный медицинский персонал', desc: '' },
  { title: 'автоматизация и защищённый документооборот', desc: '' },
  { title: 'партнёрство с сетью медицинских центров', desc: '' },
]

onMounted(async () => {
  await nextTick()
  const isMobile = window.innerWidth <= 768

  if (!isMobile) {
    // --- Десктоп ---
    gsap.from('.steps-title', {
      opacity: 0,
      x: -50,
      duration: 1,
      ease: 'power2.out',
      scrollTrigger: {
        trigger: stepsSection.value,
        start: 'top center',
      },
    })

    const tl = gsap.timeline({
      scrollTrigger: {
        trigger: stepsSection.value,
        start: 'top 80%',
        end: 'bottom 30%',
        scrub: true,
      },
    })

    stepRefs.forEach((el, index) => {
      const circle = el.querySelector('.circle-bg')
      tl.fromTo(
        circle,
        { opacity: 0, scale: 0.5 },
        { opacity: 1, scale: 1, duration: 1.2, ease: 'power2.out' },
        index * 0.4
      )
    })

    ScrollTrigger.create({
      trigger: stepsSection.value,
      start: 'top top',
      end: '+=1200',
      scrub: true,
      pin: '.steps-left',
      pinSpacing: false,
    })
  } else {
    // --- Мобильная версия ---
    const groups = [
      stepRefs.slice(0, 2),
      stepRefs.slice(2, 4),
      [stepRefs[4]],
    ]

    groups.forEach((group, i) => {
      const trigger = group[0] || stepsSection.value

      gsap.timeline({
        scrollTrigger: {
          trigger,
          start: `top ${90 - i * 20}%`,
          end: 'bottom 60%',
          toggleActions: 'play none none reverse',
        },
      }).fromTo(
        group.map(el => el.querySelector('.circle-bg')),
        { opacity: 0, scale: 0.5 },
        {
          opacity: 1,
          scale: 1,
          duration: 1,
          stagger: 0.2,
          ease: 'power2.out',
        }
      )
    })
  }
})
</script>

<template>
  <section class="steps-section" ref="stepsSection">
    <div class="steps-wrapper">
      <div class="steps-left">
        <h2 class="steps-title">
          целая система, <br />а не просто медицинский осмотр
        </h2>
        <p class="edo-note">
          <a href="#contact" class="cta-button">связаться</a>
        </p>
      </div>

      <div class="steps-right">
        <template v-for="(step, i) in steps" :key="i">
          <div class="step" :ref="el => (stepRefs[i] = el)">
            <div class="circle-bg"></div>
            <div class="step-number">{{ step.title }}</div>
          </div>
        </template>
      </div>
    </div>
  </section>
</template>

<style scoped>
.steps-section {
  padding: 80px 20px;
  background: #fff;
  font-family: sans-serif;
}

/* --- Макет --- */
.steps-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: start;
}

/* Левая часть */
.steps-left {
  position: sticky;
  top: 100px;
  padding-left: 5%;
}

.steps-title {
  font-size: clamp(36px, 6vw, 100px);
  font-weight: 100;
  color: #222;
}

.cta-button {
  display: inline-block;
  background: linear-gradient(90deg, #0050ff, #4a90ff);
  color: white;
  font-size: 36px;
  padding: 10px 30px;
  border-radius: 40px;
  text-decoration: none;
  margin-top: 20px;
}

/* Правая часть */
.steps-right {
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Круг */
.step {
  width: 450px;
  height: 450px;
  margin-top: -100px;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.step:first-child {
  margin-top: 0;
}

.circle-bg {
  position: absolute;
  width: 100%;
  height: 100%;
  border: 2px solid #bbb;
  border-radius: 50%;
  background: #fff;
  opacity: 0;
  transform: scale(0.5);
}

.step-number {
  position: relative;
  z-index: 2;
  font-size: 26px;
  font-weight: 700;
  color: #000;
  text-align: center;
}

/* --- Мобильная версия --- */
@media (max-width: 768px) {
  .steps-wrapper {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .steps-right {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 30px 20px;
    justify-items: center;
  }

  .step:nth-child(5) {
    grid-column: 1 / -1;
    justify-self: center;
  }

  .step {
    width: 160px;
    height: 160px;
    margin-top: 0;
  }

  .step-number {
    font-size: 14px;
  }

  .steps-left {
    position: static;
    text-align: center;
    padding-left: 0;
  }

  .steps-title {
    display: none;
  }

  .cta-button {
    display: none;
  }
}
</style>
