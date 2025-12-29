<script setup lang="ts">
import { onMounted, ref } from 'vue'
import bgImage from '@/assets/doc.png'


const background = ref<HTMLElement | null>(null)

function handleMouseMove(e: MouseEvent) {
  if (window.innerWidth < 1024) return
  const x = (e.clientX / window.innerWidth - 0.5) * 20
  const y = (e.clientY / window.innerHeight - 0.5) * 20
  if (background.value) {
    background.value.style.transform = `translate(${x}px, ${y}px)`
  }
}

onMounted(() => {
  const words = document.querySelectorAll('.headline .word')
  if (words.length >= 3) {
    document.documentElement.style.setProperty('--first-len', words[0].textContent?.length.toString() || '9')
    document.documentElement.style.setProperty('--second-len', words[1].textContent?.length.toString() || '10')
  }
})
</script>

<template>
  <section class="hero" @mousemove="handleMouseMove">
    <div class="hero-bg" ref="background"></div>

    <div class="hero-content">
      <!-- 📍 Фиксированный блок в верхнем левом углу -->
<!--      <div class="brand fixed-brand">-->
<!--    <img src="@/assets/logo2.svg" alt="Логотип" class="logo" />-->
<!--    <p class="brand-sub textt">-->
<!--      медицинское обеспечение <br /> промышленных предприятий-->
<!--    </p>-->
<!--  </div>-->

      <div class="hero-left">
        <div class="headline">
          <h1 class="word first zagol">скорость.</h1>
          <h1 class="word second zagol">экспертиза.</h1>
          <h1 class="word third zagol">вовлечённость.</h1>
        </div>

        <div class="cta-and-features">
          <a href="#contact" class="cta textt">связаться</a>

          <ul class="features">
            <li class="textt">→ более 100 сотрудников</li>
            <li class="textt">→ вовремя сдаём отчётность</li>
            <li class="textt">→ опытная команда</li>
            <li class="textt">→ ориентируемся на заказчика</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  overflow: hidden;
  background: #0D72B9;
  color: #000000;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: "Helvetica Neue", Arial, sans-serif;
}

.hero-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 110%;
  height: 110%;
  background: url('@/assets/doc.png') center center / cover no-repeat;
  transition: transform 0.2s ease;
  z-index: 0;
  pointer-events: none;
}


.hero-content {
  position: relative;
  z-index: 1;
  width: 90%;
  max-width: 1600px;
  padding: 40px 0;
}

/* ✅ Фиксируем бренд в левом верхнем углу */
.fixed-brand {
  position: fixed;
  top: 30px;
  left: 40px;
  z-index: 10;
  text-align: left;
}

.brand-top {
  font-size: clamp(18px, 2vw, 28px);
  font-weight: 700;
  text-transform: lowercase;
}

.brand-sub {
  font-size: clamp(16px, 1.5vw, 22px);
  color: #000000;
  margin-top: 5px;
  line-height: 1.3;
}

/* === Заголовки === */
.headline {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.word {
  font-size: clamp(44px, 8vw, 110px);
  font-weight: 900;
  line-height: 1.05;
  margin: 0;
  white-space: nowrap;
}

/* Точное выравнивание */
.word.second {
  margin-left: calc(0.72ch * var(--first-len, 9));
}

.word.third {
  margin-left: calc(1.35ch * var(--second-len, 10));
}

/* === Кнопка + список === */
.cta-and-features {
  display: flex;
  align-items: flex-start;
  gap: 60px;
  flex-wrap: wrap;
  margin-top: 40px;
}

.cta {
  background: linear-gradient(90deg, #0050ff, #4a90ff);
  color: white;
  font-size: clamp(18px, 2.5vw, 32px);
  padding: 14px 40px;
  border-radius: 50px;
  text-decoration: none;
  transition: all 0.3s ease;
  white-space: nowrap;
}

.cta:hover {
  background: #0039c8;
}

.features {
  list-style: none;
  margin: 0;
  padding: 0;
  display: grid;
  grid-template-columns: repeat(2, minmax(200px, 1fr));
  gap: 10px 30px;
  align-items: start;
  flex: 1;
}

.features li {
  font-size: clamp(18px, 2vw, 42px);
  color: #000000;
}

/* === Адаптив === */
@media (max-width: 768px) {
  .fixed-brand {

    top: 20px;
    left: 20px;
    text-align: left;
  }

  .cta-and-features {
    flex-direction: column;
    align-items: center;
    gap: 24px;
  }

  .features {
    grid-template-columns: 1fr;
    position: relative;
    top: 107px;

  }
}


/* === Адаптив === */
@media (max-width: 768px) {
  .fixed-brand {
    top: 20px;
    left: 20px;
    text-align: left;
  }

  /* 📱 Правильное выравнивание заголовков */
  .headline {
    align-items: flex-start; /* можно также поставить center, если хочешь по центру */
    position: relative;
        top: 87px;
  }

  .word {
    margin-left: 0 !important; /* убираем все отступы */
    text-align: left; /* или center — если нужно выровнять по центру */
  }

  .word.second,
  .word.third {
    margin-left: 0 !important; /* гарантированно без отступов */
  }

  .cta-and-features {
    flex-direction: column;

    gap: 24px;
  }

  .features {
    grid-template-columns: 1fr;

  }

  .cta{
    display: none;
  }
}

</style>
