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

      <h2 class="skills-title">что мы умеем</h2>



    <div class="skills-grid">
      <div class="skill">
        <div class="number" :ref="el => numberRefs[0] = el">1</div>
        <p>
     	Понимаем специфику вашего предприятия. Оперативно оказываем услуги и вовремя оформляем итоговую документацию
        </p>
      </div>
      <div class="skill">
        <div class="number" :ref="el => numberRefs[1] = el">2</div>
        <p>
      Работаем в вашей графике. Мы подстраиваемся под удобный для ваших сотрудников режим и географию работы
        </p>
      </div>
      <div class="skill">
        <div class="number" :ref="el => numberRefs[2] = el">3</div>
        <p>

  Рассчитываем наиболее выгодные условия и оказываем только действительно необходимые услуги
        </p>
      </div>
    </div>


    <div class="skills-grid" style="margin-top: 15px">
      <div class="skill">
        <div class="number" :ref="el => numberRefs[3] = el">4</div>
        <p>

        Разрабатываем и внедряем уникальные программы по требованиям заказчика
        </p>
      </div>
      <div class="skill">
        <div class="number" :ref="el => numberRefs[4] = el">5</div>
        <p>

         Бережно обрабатываем и строго охраняем персональные данные всех наших клиентов
        </p>
      </div>
      <div class="skill">
        <div class="number" :ref="el => numberRefs[5] = el">6</div>
        <p>

         	Предупреждаем о рисках: подскажем как не попасть под проверку и не нарушить закон. Безопасность – превыше всего
        </p>
      </div>
    </div>
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
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 40px;
  border-top: 1px solid transparent;
}

.skill {
  flex: 1 1 300px;
  max-width: 550px;
  border-left: 1px solid #000;
  padding: 0 20px;
}

.skill:first-child {
  border-left: none;
}

.number {
  font-size: 64px;
  font-weight: 300;
  margin-bottom: 20px;
  text-align: left;
  color: #0D72b9;
}

.skill p {
  font-size: 27px;
  line-height: 1.5;
  text-align: left;
}

@media (max-width: 768px) {
  .skills-grid {
    flex-direction: column;
    align-items: center;
    gap: 60px;
  }

  .skill {
    border-left: none;
    border-top: 1px solid #000;
    padding-top: 20px;
  }

  .skill:first-child {
    border-top: none;
  }
  .skills-title{
    font-size: 27px;
  }
  .number{
    font-size: 27px;
    font-weight: bold;
  }
  .skill p{
    font-size: 18px;
  }
  .skill{
    flex: 1 1 100px;
  }
  .skills-grid{
    display: flex
;
    justify-content: center;
    flex-wrap: wrap;
    gap: 40px;
    border-top: 1px solid #000000;
  }
}
</style>
