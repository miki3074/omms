<script setup lang="ts">
import { ref } from 'vue'

const cards = [
  {
    title: "Сервис по ремонту авто",
    features: ["10 сотрудников", "медицинский осмотр", "заключительная документация"],
    price: "~ 50 000 руб.",
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#2A2A2A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M3 17v-6a4 4 0 0 1 8 0v6"/>
      <rect x="1" y="17" width="20" height="5" rx="2" ry="2"/>
      <path d="M16 17v-3a4 4 0 0 1 8 0v3"/>
    </svg>`
  },
  {
    title: "Аграрный комплекс",
    features: ["200 сотрудников", "медицинский осмотр", "консультации специалистов"],
    price: "~ 500 000 руб.",
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#2A2A2A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <circle cx="12" cy="12" r="10"/>
      <path d="M8 12l2 2 4-4"/>
    </svg>`
  },
  {
    title: "Промышленный гигант",
    features: ["1000 сотрудников", "медицинский осмотр", "система динамического наблюдения", "сеть здравпунктов"],
    price: "~ 5 000 000 руб.",
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#2A2A2A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M3 12h18"/><path d="M3 6h18"/><path d="M3 18h18"/>
    </svg>`
  },
  {
    title: "Узнать стоимость услуг для вашего бизнеса",
    features: [],
    price: "",
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#2A2A2A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <circle cx="12" cy="12" r="10"/>
      <path d="M12 6v6l4 2"/>
    </svg>`
  }
]
</script>

<template>
  <section class="founders-section">
    <h2 class="why-title">Сколько это стоит</h2>
    <div class="founder-card light">
      <div class="left"></div>
      <div class="right">
        
        <p>
          <span class="link">мы - профессионалы.</span> Наш опыт – организация эффективных медицинских программ для работников и предприятий. Мы быстро и нестандартно мыслим, чтобы сделать медицинскую помощь доступной и качественной
        </p>
      </div>
    </div>

    <div class="cards-container">
      <div v-for="(card, i) in cards" :key="i" class="card">
        <div class="card-content">
          <div class="icon" v-html="card.icon" />
          <h3 class="card-title">{{ card.title }}</h3>
          <ul class="card-list" v-if="card.features.length">
            <li v-for="(item, idx) in card.features" :key="idx" class="card-list-item">{{ item }}</li>
          </ul>
          <div class="card-spacer" />
          <div class="card-price" v-if="card.price">{{ card.price }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.founders-section {
  padding: 60px 5vw;
  font-family: sans-serif;
  background: #fff;
}

.why-title {
  font-size: clamp(28px, 6vw, 57px);
  font-weight: bold;
  margin-bottom: 24px;
  color: black;
}

.founder-card {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  margin-bottom: 40px;
}

.right p {
  font-size: clamp(18px, 4vw, 54px);
  line-height: 1.6;
   margin-left: clamp(0px, 5vw, 19%);
}

.link {
  color: #0070f3;
  font-weight: 600;
}

.cards-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.card {
  background: white;
  border-radius: 12px;
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.06);
  transition: box-shadow 0.3s ease;
  display: flex;
  flex-direction: column;
  padding: 32px 24px;
}

.card:hover {
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.12);
}

.card-title {
  font-size: clamp(18px, 2vw, 24px);
  font-weight: 700;
  text-align: center;
  margin-bottom: 18px;
}

.card-list {
  list-style: none;
  padding: 0;
  font-size: clamp(14px, 1.6vw, 16px);
  text-align: center;
  margin-bottom: 20px;
}

.card-list-item {
  margin-bottom: 8px;
}

.card-price {
  font-size: clamp(16px, 2vw, 20px);
  font-weight: 700;
  color: #ff7f50;
  text-align: center;
}

.icon {
  width: 48px;
  height: 48px;
  margin: 0 auto 20px auto;
}
</style>
