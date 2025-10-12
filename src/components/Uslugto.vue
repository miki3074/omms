<script setup>
const services = [
  {
    title: 'Предварительные медосмотры',
    subtitle: 'При приеме на работу',
    points: [
      'Полное обследование кандидатов',
      'Определение профпригодности',
      'Оформление медицинских заключений',
    ],
  },
  {
    title: 'Периодические медосмотры',
    subtitle: 'Плановые обследования персонала',
    points: [
      'График, согласованный с предприятием',
      'Выявление профзаболеваний на ранних стадиях',
      'Осмотры стажированного контингента',
    ],
  },
  {
    title: 'Предрейсовые / предсменные медосмотры',
    subtitle: 'Для водителей и других специальностей',
    points: [
      'Оперативный вывод на линию',
      'Внедрение современных медицинских комплексов',
      'Формирование электронных путевых листов',
    ],
  },
  {
    title: 'Психофизиологические обследования',
    subtitle: 'Для ответственных должностей',
    points: [
      'Тестирование скорости реакции',
      'Проверка когнитивных функций',
      'Оценка стрессоустойчивости',
    ],
  },
  {
    title: 'Защищенный электронный документооборот',
    subtitle: 'Для всех контрагентов',
    points: [
      'Защита персональных данных работников',
      'Безопасный обмен списками',
      'Оперативное получение заключений',
    ],
  },
]
</script>

<template>
  <section class="services-section">
    <div class="services-grid">
      <div v-for="(service, index) in services" :key="index" class="service-card">
        <div class="service-number">{{ index + 1 }}.</div>
        <h3 class="service-title">{{ service.title }}</h3>
        <p class="service-subtitle">{{ service.subtitle }}</p>
        <ul class="service-list">
          <li v-for="(item, i) in service.points" :key="i">{{ item }}</li>
        </ul>
      </div>
    </div>
  </section>
</template>

<style scoped>
.services-section {
  padding: 60px 5vw;
  background: #f5f5f5;
  font-family: sans-serif;
}

.services-title {
  font-size: clamp(28px, 5vw, 48px);
  font-weight: 700;
  margin-bottom: 40px;
  text-align: left;
  color: #0d72b9;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}

.service-card {
  background: white;
  padding: 24px;
  border-radius: 12px;
  box-shadow: 0 4px 14px rgba(0, 0, 0, 0.06);
  transition: transform 0.3s ease;
}

.service-card:hover {
  transform: translateY(-5px);
}

.service-number {
  font-size: 32px;
  font-weight: bold;
  color: #e72d50;
  margin-bottom: 10px;
}

.service-title {
  font-size: 22px;
  font-weight: 600;
  color: #222;
  margin-bottom: 6px;
}

.service-subtitle {
  font-size: 16px;
  font-style: italic;
  color: #666;
  margin-bottom: 12px;
}

.service-list {
  list-style: disc;
  padding-left: 20px;
  font-size: 16px;
  color: #444;
}

@media (max-width: 768px) {
  .services-title {
    text-align: center;
  }
  .service-number {
    font-size: 24px;
  }
  .service-title {
    font-size: 18px;
  }
  .service-subtitle {
    font-size: 14px;
  }
  .service-list {
    font-size: 14px;
  }
}
</style>
