<script setup lang="ts">
import { ref, onMounted, nextTick } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const sectionRef = ref<HTMLElement | null>(null)

const leftTitle = 'почему мы крутые'

interface WhyLeftItem {
  number: number
  text: string
}

const leftItems = ref<WhyLeftItem[]>([
  { number: 1, text: 'мы предлагаем коллективный разум, экспертность и целую систему, работающую как слаженный оркестр, а не просто знания отдельных специалистов.' },
  { number: 2, text: 'отвечаем на запросы за 5 минут, не пропадаем и не срываем сроки. Не болеем, не уходим в отпуск, не отпрашиваемся пораньше в пятницу.' },
  { number: 3, text: 'активная позиция: мы не ждём, когда всё само как-то произойдёт, а действуем на опережение, советуем и подсказываем.' },
  { number: 4, text: 'постоянно учимся и повышаем квалификацию.' },
  { number: 5, text: 'сервис по ремонту авто, аграрный комплекс или промышленный гигант – наша команда справляется с медицинским обеспечением в самых разных сферах.' },
  { number: 6, text: 'строгое соблюдение врачебной тайны + защищённая IT-часть.' }
])

interface WhyItem {
  icon: string
  title: string
  text: string
  num: string
}

const rightItems = ref<WhyItem[]>([
  { icon: '🚫', num: '1', title: 'Поликлиники и районные больницы', text: 'Имеют огромные коллективы, но слишком сильно зависят от навыков и знаний нескольких ключевых сотрудников. Если важный сотрудник уходит в отпуск или увольняется, это заметно влияет на качество услуг, так как работает не система, а конкретный человек' },
  { icon: '🚫', num: '1', title: 'Другие частные клиники', text: 'Обычно стремятся сэкономить на всем, даже на составе врачебных бригад, что часто снижает качество услуг и создает потенциальные проблемы для работодателя' },
  { icon: '🚫', num: '2', title: 'Поликлиники и районные больницы', text: 'Ответственные лица не всегда реагируют на запросы, часто отпрашиваются пораньше, уходят на больничный и в отпуск.' },
  { icon: '🚫', num: '2', title: 'Другие частные клиники', text: 'Как повезёт: если клиника попадётся ответственная, скорее всего, она будет стараться отвечать оперативно и не пропадет в ответственный момент. А может попасться и та, которой всё равно. Шансы – 50/50.' },
  { icon: '🚫', num: '3', title: 'Поликлиники и районные больницы', text: 'Обычно работают не ПРОактивно, а РЕактивно: пока не дёрнешь, не делают. Поверьте, уж мы-то знаем – работаем в этой сфере более 10 лет.' },
  { icon: '🚫', num: '3', title: 'Другие частные клиники', text: 'Из-за отсутствия системы, по сути, работают в режиме пожарника: загорелось – потушили. Когда звонит заказчик, часто реагируют в стиле «вас много, а я одна».' },
  { icon: '🚫', num: '4', title: 'Поликлиники и районные больницы', text: 'Относятся к медицинским осмотрам только как к дополнительной внебюджетной деятельности и часто считают, что опыта и знаний уже хватает, поэтому не уделяют много внимания обучению.' },
  { icon: '🚫', num: '4', title: 'Другие частные клиники', text: 'Отсутствует система – часто не хватает даже базовых медицинских специалистов. Поэтому если клиника суперответственная, она будет повышать квалификацию сотрудников, а если нет – будет надеяться на старый опыт. Как повезёт.' },
  { icon: '🚫', num: '5', title: 'Поликлиники и районные больницы', text: 'Как правило, разбираются в ограниченном числе сфер – исходя из опыта работы с близлежащими заказчиками.' },
  { icon: '🚫', num: '5', title: 'Другие частные клиники', text: 'Как правило, разбираются в тонкостях различных сфер, но часто отдают предпочтение лишь высокомаржинальным заказам' },
  { icon: '🚫', num: '6', title: 'Поликлиники и районные больницы', text: 'Увы, частый кейс, когда ответственное лицо со сменой места работы использует ранее полученные данные заказчиков.' },
  { icon: '🚫', num: '6', title: 'Другие частные клиники', text: 'Стараются сохранить информацию клиентов в тайне, но часто уязвимы для кибератак.' }
])

const leftHeights = ref<number[]>([])

onMounted(async () => {
  await nextTick()

  const groups = document.querySelectorAll('.why-right-group')
  const heights = Array.from(groups).map(g => g.clientHeight)
  leftHeights.value = heights

  const left = document.querySelector('.why-left') as HTMLElement
  const right = document.querySelector('.why-right') as HTMLElement
  const wrapper = document.querySelector('.why-wrapper') as HTMLElement
  const leftTitleEl = document.querySelector('.why-title') as HTMLElement
  const leftItemsEls = document.querySelectorAll('.why-left-item')

  if (left && right && wrapper && leftTitleEl) {
    // Рассчитываем сумму высот всех пунктов до 6-го (индекс 5) включительно
    const totalHeightUntil6 = heights.slice(0, 6).reduce((acc, h) => acc + h, 0)
    // Добавляем половину высоты 6-го пункта
    const middleOf6 = totalHeightUntil6 - heights[5] / 2

    // Фиксируем заголовок и пиним его до середины 6-го пункта
    ScrollTrigger.create({
      trigger: wrapper,
      start: 'top top',
      end: () => `+=${middleOf6}`,  // конец пина - середина 6-го пункта справа
      pin: leftTitleEl,
      pinSpacing: false,
      scrub: false,
    })

    // Анимация для левых блоков (как у тебя была)
    leftItemsEls.forEach((el, i) => {
      const height = heights[i]
      gsap.fromTo(el, 
        { y: 0, opacity: 1 },
        {
          y: +height,
          opacity: 0,
          ease: 'none',
          scrollTrigger: {
            trigger: wrapper,
            start: () => `top+=${heights.slice(0, i).reduce((a,b)=>a+b,0)} top`,
            end: () => `top+=${heights.slice(0, i+1).reduce((a,b)=>a+b,0)} top`,
            scrub: true,
            invalidateOnRefresh: true,
          }
        }
      )
    })
  }
})

</script>

<template>
  <section class="why-section" ref="sectionRef">
    <div class="why-wrapper">
      <div class="why-left">
        <h2 class="why-title">{{ leftTitle }}</h2>

        <div
          class="why-left-item"
          v-for="(item, index) in leftItems"
          :key="item.number"
          :style="{ height: leftHeights[index] + 'px', overflow: 'hidden' }"
        >
          <div class="why-left-number">{{ item.number }})</div>
          <div class="why-left-text">{{ item.text }}</div>
        </div>
      </div>

      <div class="why-right">
        <div
          class="why-right-group"
          v-for="num in 6"
          :key="num"
        >
          <div
            class="why-item"
            v-for="item in rightItems.filter(i => i.num === num.toString())"
            :key="item.title"
          >
            <div class="why-icon">{{ item.icon }}</div>
            <div class="why-content">
              <h3>{{ item.title }}</h3>
              <p>{{ item.text }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.why-section {
  padding: 80px 40px;
  background-color: #fff;
  font-family: sans-serif;
}

.why-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: flex-start;
  position: relative;
}

.why-left {
  text-align: left;
  padding-left: 19%;
  position: relative;
  z-index: 10; /* Чтобы заголовок перекрывал элементы */
}

.why-title {
  font-size: 57px;
  font-weight: bold;
  margin-bottom: 24px;
  color: black;
  position: relative;
  background: white; /* Чтобы было эффект перекрытия */
  z-index: 20;
  padding-bottom: 10px;
}

.why-left-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 20px;
  overflow: hidden;
  position: relative;
}

.why-left-number {
  font-weight: bold;
  margin-right: 10px;
  min-width: 24px;
  font-size: 24px;
}

.why-left-text {
  line-height: 1.6;
  font-size: 39px;
}

/* Правая колонка */

.why-right-group {
  margin-bottom: 40px;
}

.why-item {
  display: flex;
  align-items: flex-start;
  gap: 20px;
  margin-bottom: 20px;
}

.why-icon {
  font-size: 24px;
  margin-top: 6px;
  min-width: 30px;
}

.why-content h3 {
  margin: 0 0 10px;
  font-size: 40px;
  font-weight: 700;
  color: #000;
}

.why-content p {
  font-size: 39px;
  line-height: 1.5;
  color: #222;
}

/* Адаптив */
@media (max-width: 768px) {
  .why-wrapper {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .why-title {
    font-size: 32px;
  }

  .why-left-text {
    font-size: 16px;
  }

  .why-left-number {
    font-size: 18px;
  }

  .why-item {
    flex-direction: row;
    gap: 16px;
  }
}
</style>
