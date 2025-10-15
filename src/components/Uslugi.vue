<script setup lang="ts">
import { ref } from 'vue'
import { ElDialog } from 'element-plus'
import { BottomLeft } from '@element-plus/icons-vue'

interface Section {
  title: string
  subtitle: string
  points: string[]
}

const sections: Section[] = [
  {
    title: 'Предварительные и периодические медосмотры',
    subtitle: 'При приеме на работу',
    points: [
      'Здоровый сотрудник – продуктивный сотрудник. Мы помогаем поддерживать работоспособность коллектива...'
    ]
  },
  {
    title: 'Предрейсовые и предсменные медосмотры',
    subtitle: 'Контроль безопасности сотрудников',
    points: [
      'Систематический контроль – главный фактор предотвращения ДТП и несчастных случаев...'
    ]
  },
  {
    title: 'Медицинские освидетельствования',
    subtitle: 'Психиатрические и наркологические освидетельствования',
    points: [
      'Допуск к работе сотрудников, чья деятельность связана с повышенной опасностью...'
    ]
  },
  {
    title: 'Единое окно',
    subtitle: 'Единое окно медицинских услуг',
    points: [
      'Мы предлагаем организацию всех видов обязательных медицинских мероприятий по принципу «единого окна».'
    ]
  },
  {
    title: 'Психофизиологическое обследование',
    subtitle: 'Оценка надежности персонала',
    points: [
      'Быстрая реакция, устойчивое внимание, стрессоустойчивость – ключевые качества...'
    ]
  },
  {
    title: 'Телемедицинские консультации',
    subtitle: 'Современные технологии медицины',
    points: [
      'Сократите простои и повысьте производительность с помощью телемедицины...'
    ]
  },
  {
    title: 'Электронный документооборот',
    subtitle: 'Безбумажное взаимодействие',
    points: [
      'Внедряем защищённый электронный документооборот (ЭДО)...'
    ]
  },
  {
    title: 'Комплексное медицинское обеспечение',
    subtitle: 'Полный цикл медицинских услуг',
    points: [
      'Единый контракт, персональный менеджер и полная ответственность за все медицинские процессы...'
    ]
  }
]


const dialogZoom = ref(1.5) // Можно менять динамически

const dialogVisible = ref(false)
const activeSection = ref<Section | null>(null)

const openModal = (section: Section) => {
  activeSection.value = section
  dialogVisible.value = true
}
</script>

<template>
  <section class="features-section">
    <el-main>
      <div class="container">
        <div class="section-header">
          <h4 class="zagol"><span class="zagol">Что мы предлагаем</span></h4>
        </div>

        <div class="grid-container">
          <div
            v-for="(section, index) in sections"
            :key="index"
            class="grid-item"
            @click="openModal(section)"
          >
            <div class="icon-wrapper">
              <el-icon><BottomLeft /></el-icon>
            </div>
            <div class="item-title zagol">{{ section.title }}</div>
          </div>
        </div>

        <el-dialog
  v-model="dialogVisible"
  align-center
  width="50vw"
  :style="{ transform: `scale(${dialogZoom})`, transformOrigin: 'center center' }"
>
          <template #header>
            <h2 class="dialog-title zagol">{{ activeSection?.subtitle }}</h2>
          </template>

          <template #default>
            <div v-for="(point, i) in activeSection?.points" :key="i" class="dialog-text textt">
              {{ point }}
            </div>
            <div class="dialog-footer">
              <button class="apply-btn textt">Оставить заявку</button>
            </div>
          </template>
        </el-dialog>
      </div>
    </el-main>
  </section>
</template>

<style scoped>


.el-dialog {
  transform: scale(1.7);
}


.features-section {
  background: #f5f5f5;
  padding: 60px 5%;
}

.section-header {
  margin-bottom: 50px;
  text-align: left;
}

.section-header h4 {
  font-size: clamp(28px, 5vw, 64px);
  font-family: 'HelveticaNeue', Arial, sans-serif;
  color: #000;
  font-weight: 600;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr); /* 4 на ряд */
  gap: 24px;
}

/* Карточка */
.grid-item {
  position: relative;
  background: #fff;
  padding: 32px;
  cursor: pointer;
  transition: 0.3s ease;
  font-weight: 600;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.06);
  display: flex;
  flex-direction: column;
  justify-content: center; /* ✅ центрируем по вертикали */
  align-items: flex-start;  /* ✅ текст остаётся слева */
  min-height: 200px;

 
    
  

}


.grid-item:hover {
  background: #0d72b9;
  color: #fff;
  transform: translateY(-3px);
}

.icon-wrapper {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: clamp(36px, 4vw, 64px);
  color: #0d72b9;
}

.grid-item:hover .icon-wrapper {
  color: #fff;
}

.item-title {
  font-size: clamp(21px, 1.6vw, 26px);
  line-height: 1.3;
  word-break: break-word;
}

/* Диалог */
.dialog-title {
  font-size: clamp(14px, 3vw, 40px);
  font-weight: 600;
  
  color: #000;
}

.dialog-text {
  font-size: clamp(16px, 2vw, 38px);
  margin-bottom: 16px;
  line-height: 1.5;
  color: #333;
}

.dialog-footer {
 
  margin-top: 20px;
}

.apply-btn {
  background: #0d72b9;
  color: #fff;
  border: none;
  padding: 12px 32px;
  font-size: clamp(14px, 2vw, 18px);
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.3s;
  color: #ffffff;
    font-family: "HelveticaNeue", Arial, sans-serif;
    line-height: 1.55;
    font-weight: 400;
    border-radius: 30px 30px 30px 30px;
    background-image: linear-gradient(0.375turn, rgba(0, 66, 222, 1) 0%, rgb(0 75 255) 100%);
    border-color: transparent;
    border-style: solid;
    transition: background-color 0.2s ease-in-out, color 0.2s ease-in-out, border-color 0.2s ease-in-out;
}

.apply-btn:hover {
  background: #095a93;
}

/* --- Адаптация --- */

/* Планшеты (2 ряда × 2 карточки) */
@media (max-width: 1024px) {
  .grid-container {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Мобильные (1 карточка в ряд) */
@media (max-width: 600px) {
  .grid-container {
    grid-template-columns: 1fr;
  }

  .grid-item {
    padding: 20px;
    min-height: 120px;
  }

  .icon-wrapper {
    font-size: 32px;
  }

  .apply-btn{
    padding: 0 10px;
  }

 

}
</style>
