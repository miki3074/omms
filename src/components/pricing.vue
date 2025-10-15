<template>
  <section class="pricing">
    <div class="card" v-for="card in cards" :key="card.title">
      <div class="card-content">
          <img :src="card.icon" alt="" class="icon" />
        <div class="card-text">

          <h3>{{ card.title }}</h3>
          <ul>
            <li v-for="item in card.list" :key="item">✔ {{ item }}</li>
          </ul>
          <p class="extra">{{ card.extra }}</p>
        </div>
      
      </div>
      <p class="price">~ {{ card.price }} руб.</p>
    </div>

    <div class="cta">
      <p>Узнать <br>стоимость<br>услуг<br>для вашего<br> бизнеса</p>
    </div>
  </section>
</template>

<script setup>
import iconTooth from '@/assets/icon_tooth.svg'
import iconArrow from '@/assets/icon_arrow.svg'
import iconPaper from '@/assets/icon_paper.svg'

const cards = [
  {
    icon: iconTooth,
    title: "Стоматологическая клиника",
    list: [
      "8 сотрудников",
      "до 100 документов",
      "учёт и отчётность",
      "рассчитываем зарплаты",
    ],
    extra: "Дополнительно помогаем с платежами и кадрами",
    price: "80 000",
  },
  {
    icon: iconArrow,
    title: "Интернет-сервис",
    list: [
      "40 сотрудников",
      "до 200 документов",
      "учёт и отчётность",
      "рассчитываем зарплаты",
    ],
    extra: "Дополнительно помогаем с кадровым учётом",
    price: "120 000",
  },
  {
    icon: iconPaper,
    title: "Производство бумажных изделий",
    list: [
      "220 сотрудников",
      "до 1400 документов",
      "учёт и отчётность",
      "рассчитываем зарплаты",
    ],
    extra: "Дополнительно помогаем с ведением участка производства",
    price: "300 000",
  },
];
</script>

<style scoped>
/* --- Общий контейнер --- */
.pricing {
  display: flex;
  gap: 32px;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 80px;
  font-family: 'Lato', sans-serif;
}

/* --- Карточка --- */
.card {
  background: #f8f8f8;
  border-radius: 16px;
  padding: 40px 32px;
  width: 320px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  zoom: 1.2;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.08);
}

/* --- Внутренний контейнер для текста и иконки --- */
.card-content {
  display: flex;
  flex-direction: column; /* по умолчанию — иконка сверху */
  align-items: flex-start;
  gap: 16px;
}

/* --- Иконка --- */
.icon {
  width: 56px;
  height: 56px;
}

/* --- Заголовок и текст --- */
.card-text {
  flex: 1;
}

.card h3 {
  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
  font-size: 23px;
  margin-bottom: 16px;
}

.card ul {
  padding-left: 0;
  list-style: none;
  margin-bottom: 16px;
}

.card li {
  margin-bottom: 8px;
  font-size: 16px;
}

.extra {
  font-size: 15px;
  line-height: 1.5;
  color: #333;
  margin-bottom: 20px;
}

/* --- Цена --- */
.price {
  font-weight: 700;
  font-size: 22px;
  margin-top: 16px;
}

/* --- Синяя CTA-кнопка --- */
.cta {
  background: linear-gradient(180deg, #2a6df6, #0053f0);
  color: white;
  border-radius: 16px;
  width: 320px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 40px 24px;
  font-weight: 600;
  font-size: 20px;
  cursor: pointer;
  transition: background 0.3s ease;
}

.cta:hover {
  background: linear-gradient(180deg, #0053f0, #003de0);
}

/* --- 📱 Мобильная версия --- */
@media (max-width: 768px) {
  .card {
    width: 100%;
    padding: 28px 24px;
    zoom: 1;
  }

  .card-content {
    flex-direction: row-reverse; /* иконка справа */
    align-items: flex-start;
    justify-content: space-between;
  }

  .card-text {
    flex: 1;
  }

  .icon {
    width: 48px;
    height: 48px;
    margin-left: 16px;
  }

  .card h3 {
    font-size: 20px;
  }

  .price {
    font-size: 20px;
  }
}
</style>
