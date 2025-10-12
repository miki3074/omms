<script setup lang="ts">
import { onMounted, ref } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'
import Map from '@/components/map.vue'

gsap.registerPlugin(ScrollTrigger)

const numberRefs: HTMLElement[] = []

onMounted(() => {
  const isMobile = window.innerWidth <= 768

  numberRefs.forEach((el, i) => {
    if (isMobile) {
      // На мобильных — показываем сразу
      el.style.opacity = '1'
      el.style.transform = 'none'
    } else {
      // На десктопах — с анимацией
      gsap.from(el, {
        opacity: 0,
        y: 30,
        duration: 0.6,
        delay: i * 0.2,
        scrollTrigger: {
          trigger: el,
          start: 'top 90%',
          toggleActions: 'play none none none',
        },
      })
    }
  })
})

</script>

<template>
  <section class="skills">
    <h2 class="skills-title">Наши преимущества</h2>

    <!-- Первый ряд -->
    <div class="skills-grid">
      <div class="skill">
        <div class="number" :ref="el => numberRefs[0] = el">1</div>
        <p>
          <span class="highlight">География медицинских площадок:</span><br />
          Казань, Набережные Челны, Нижнекамск, Елабуга, Альметьевск, Лениногорск
        </p>
      </div>
      <div class="skill">
        <div class="number" :ref="el => numberRefs[1] = el">2</div>
        <p>
          <span class="highlight">Медицинские специалисты</span><br />
          с опытом работы на промышленных предприятиях
        </p>
      </div>
      <div class="skill">
        <div class="number" :ref="el => numberRefs[2] = el">3</div>
          <p>
          
          <span class="highlight">Индивидуальный подход</span><br />
          Учет специфики вашего производства и особенностей закупочных процедур.
        </p>
      </div>
    </div>

    <!-- Второй ряд -->
    <div class="skills-grid" style="margin-top: 15px">
      <div class="skill">
        <div class="number" :ref="el => numberRefs[3] = el">4</div>
        <p>
          <span class="highlight">Юридическая гарантия</span><br />
          Все заключения соответствуют требованиям Роспотребнадзора и трудового законодательства.
        </p>
      </div>
      <div class="skill">
        <div class="number" :ref="el => numberRefs[4] = el">5</div>
        <p>
          <span class="highlight">Сроки "под ключ"</span><br />
          От составления списка работников до сдачи отчетности в контролирующие органы.
        </p>
      </div>
      <div class="skill">
        <div class="number" :ref="el => numberRefs[5] = el">6</div>
           <span class="highlight">Гибкая ценовая политика</span>
      
      </div>
    </div>

    <!-- Карта внизу -->
    <Map />
  </section>
</template>

<style scoped>
.skills {
  padding: 60px 20px;
  font-family: sans-serif;
  text-align: center;
}

.skills-title {
  font-size: 48px;
  font-weight: 600;
  margin-bottom: 40px;
  text-align: left;
  padding-left: 5%;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 40px;
  justify-content: center;
  border-top: 1px solid transparent;
}

.skill {
  border-left: none;
  padding: 0 20px;
  text-align: left;
}

.skill:first-child {
  border-left: none;
}

.number {
  font-size: 64px;
  font-weight: 300;
  margin-bottom: 20px;
  color: #0D72b9;
}

.skill p {
  font-size: 27px;
  line-height: 1.5;
}

.highlight {
  color: #e72d50;
  font-weight: bold;
}

@media (max-width: 768px) {
  .skills-title {
    font-size: 27px;
  }

  .number {
    font-size: 27px;
    font-weight: bold;
  }

  .skill p {
    font-size: 18px;
  }

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
  margin-bottom: 40px;
}

.skill {
  min-height: 0px; /* или auto при необходимости */
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

  .skill:first-child {
    border-top: none;
  }
}
</style>
