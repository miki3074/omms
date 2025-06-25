<script setup lang="ts">
import { ref } from 'vue'

// Активный раскрытый индекс
const activeIndex = ref<number | null>(null)

function toggle(index: number) {
  activeIndex.value = activeIndex.value === index ? null : index
}

// Данные левой колонки
const leftTitle = 'почему мы крутые'

interface WhyLeftItem {
  number: number
  text: string
}

const leftItems = ref<WhyLeftItem[]>([
  { number: 1, text: 'мы предлагаем коллективный разум, экспертность и целую систему, работающую как слаженный оркестр.' },
  { number: 2, text: 'отвечаем на запросы за 5 минут, не пропадаем и не срываем сроки.' },
  { number: 3, text: 'активная позиция: мы действуем на опережение, советуем и подсказываем.' },
  { number: 4, text: 'постоянно учимся и повышаем квалификацию.' },
  { number: 5, text: 'справляемся с медицинским обеспечением в самых разных сферах.' },
  { number: 6, text: 'строгое соблюдение врачебной тайны + защищённая IT-часть.' }
])

// Данные правой (встроенной) части
interface WhyItem {
  icon: string
  title: string
  text: string
  num: string
}

const rightItems = ref<WhyItem[]>([
  { icon: '🚫', num: '1', title: 'Поликлиники', text: 'Сильно зависят от ключевых сотрудников.' },
  { icon: '🚫', num: '1', title: 'Частные клиники', text: 'Экономят на врачах, страдает качество.' },

  { icon: '🚫', num: '2', title: 'Поликлиники', text: 'Часто не реагируют на запросы вовремя.' },
  { icon: '🚫', num: '2', title: 'Частные клиники', text: 'Как повезёт — могут игнорировать.' },

  { icon: '🚫', num: '3', title: 'Поликлиники', text: 'Реагируют, только когда нужно тушить пожар.' },
  { icon: '🚫', num: '3', title: 'Частные клиники', text: 'Нет системности, только реакция.' },

  { icon: '🚫', num: '4', title: 'Поликлиники', text: 'Считают, что учиться не нужно.' },
  { icon: '🚫', num: '4', title: 'Частные клиники', text: 'Учеба зависит от руководства.' },

  { icon: '🚫', num: '5', title: 'Поликлиники', text: 'Работают с ограниченным кругом клиентов.' },
  { icon: '🚫', num: '5', title: 'Частные клиники', text: 'Выбирают только выгодных заказчиков.' },

  { icon: '🚫', num: '6', title: 'Поликлиники', text: 'Бывают утечки данных после увольнения.' },
  { icon: '🚫', num: '6', title: 'Частные клиники', text: 'Есть риски кибератак.' }
])
</script>

<template>
  <section class="why-section">
    <div class="why-left">
      <h2 class="why-title">{{ leftTitle }}</h2>

      <div
        v-for="(item, index) in leftItems"
        :key="item.number"
        class="why-left-item"
      >
        <div class="why-left-number">{{ item.number }})</div>
        <div class="why-left-text">{{ item.text }}</div>

        <button class="toggle-btn" @click="toggle(index)">
          {{ activeIndex === index ? 'Скрыть' : 'А как у других?' }}
        </button>

        <!-- Встроенный блок под каждым пунктом -->
        <transition name="fade">
          <div
            v-if="activeIndex === index"
            class="why-alt-block"
          >
            <div
              class="why-item"
              v-for="alt in rightItems.filter(i => i.num === item.number.toString())"
              :key="alt.title"
            >
              <div class="why-icon">{{ alt.icon }}</div>
              <div class="why-content">
                <h3>{{ alt.title }}</h3>
                <p>{{ alt.text }}</p>
              </div>
            </div>
          </div>
        </transition>
      </div>
    </div>
  </section>
</template>

<style scoped>
.why-section {
  padding: 60px 30px;
  background-color: #f9f9f9;
  font-family: sans-serif;
  max-width: 900px;
  margin: auto;
}

.why-title {
  font-size: 32px;
  margin-bottom: 30px;
  font-weight: bold;
}

.why-left-item {
  margin-bottom: 30px;
  padding-bottom: 10px;
  border-bottom: 1px solid #ddd;
}

.why-left-number {
  font-weight: bold;
  font-size: 22px;
  margin-bottom: 6px;
}

.why-left-text {
  font-size: 18px;
  line-height: 1.5;
  margin-bottom: 10px;
}

.toggle-btn {
  background: none;
  border: none;
  color: #0050ff;
  font-size: 16px;
  cursor: pointer;
  font-weight: bold;
  padding: 0;
  margin-bottom: 10px;
}

.why-alt-block {
  background-color: #fff;
  border-left: 4px solid #0050ff;
  padding: 12px 16px;
  margin-top: 10px;
  border-radius: 6px;
}

.why-item {
  margin-bottom: 12px;
}

.why-icon {
  font-size: 20px;
  margin-bottom: 4px;
}

.why-content h3 {
  margin: 0 0 4px;
  font-size: 18px;
  font-weight: 600;
}

.why-content p {
  margin: 0;
  font-size: 16px;
  color: #333;
}

/* Плавное появление блока */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

@media (max-width: 768px) {
  .why-section {
    padding: 40px 16px;
  }

  .why-title {
    font-size: 27px;
  }

  .why-left-text {
    font-size: 18px;
  }

  .toggle-btn {
    font-size: 15px;
  }

  .why-content h3 {
    font-size: 18px;
  }

  .why-content p {
    font-size: 18px;
  }
}
</style>
