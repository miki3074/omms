<script setup>
import { ref, onMounted, getCurrentInstance } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const steps = [
  'Заявка от предприятия',
  'Заключение договора',
  'Проведение осмотров',
  'Оформление заключений',
  'Передача отчетности',
]

const stepRefs = ref([]) // Vue автоматически соберёт все элементы с ref="stepRefs" в массив

onMounted(() => {
  if (window.innerWidth <= 600) {
    // Мобильная версия — не запускаем анимацию
    return
  }

  stepRefs.value.forEach((el, i) => {
    gsap.from(el, {
      opacity: 0,
      y: 50,
      duration: 0.8,
      delay: i * 0.1,
      scrollTrigger: {
        trigger: el,
        start: 'top 80%',
        toggleActions: 'play none none none',
      },
    })
  })
})

</script>

<template>
  <section class="work-steps">
    <h2 class="section-title">Как мы работаем</h2>
    <div class="timeline">
      <div
        v-for="(step, index) in steps"
        :key="index"
        class="timeline-step"
        ref="stepRefs"
      >
        <div class="circle">{{ index + 1 }}</div>
        <div class="text">{{ step }}</div>
      </div>
    </div>
    <p class="edo-note">
      Весь документооборот реализуется в безвозмездно представленном <strong>защищённом ЭДО</strong>.
    </p>
  </section>
</template>

<style scoped>
.work-steps {
  padding: 60px 20px;
  background-color: #f8f8f8;
  font-family: sans-serif;
  text-align: center;
}

.section-title {
  font-size: clamp(24px, 5vw, 48px);
  font-weight: bold;
  margin-bottom: 40px;
}

.timeline {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  gap: 40px;
  max-width: 700px;
  margin: 0 auto;
}

.timeline-step {
  display: flex;
  align-items: center;
  gap: 20px;
  background: white;
  padding: 20px 30px;
  border-radius: 12px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.05);
  width: 100%;
  max-width: 600px;
}

.circle {
  background-color: #0d72b9;
  color: white;
  font-weight: bold;
  font-size: 20px;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.text {
  font-size: clamp(16px, 2vw, 22px);
  text-align: left;
  flex: 1;
}

.edo-note {
  margin-top: 40px;
  font-size: clamp(16px, 2vw, 20px);
  max-width: 700px;
  margin-inline: auto;
  color: #333;
  font-style: italic;
}

@media (max-width: 600px) {
  .timeline-step {
    flex-direction: row;
    align-items: center;
    gap: 12px;
    width: 81%;
  }

  .circle {
    flex-shrink: 0;
  }

  .text {
    text-align: left;
  }
}

</style>
