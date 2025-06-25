<script setup lang="ts">

</script>

<template>
  <section class="founders-section">
    <h2 class="why-title">Сколько это стоит</h2>
    <!-- Первый блок -->
    <div class="founder-card light">
      <div class="left" style="    flex: 1 1 1%;">
      
      </div>
      <div class="right">
        <p>

          <span class="link">мы - профессионалы.</span> Наш опыт – организация эффективных медицинских программ для работников и предприятий. Мы быстро и нестандартно мыслим, чтобы сделать медицинскую помощь доступной и качественной

        </p>
      </div>
    </div>

  
  <el-row :gutter="32" class="cards-container">
    <el-col
      :xs="24"
      :sm="12"
      :md="12"
      :lg="6"
      v-for="(card, i) in cards"
      :key="i"
      class="card-column"
    >
      <el-card class="card" shadow="never">
        <div class="card-content">
          <div class="icon" v-html="card.icon"></div>
          <h3 class="card-title">{{ card.title }}</h3>
          <ul class="card-list" v-if="card.features.length">
            <li v-for="(item, idx) in card.features" :key="idx" class="card-list-item">
              {{ item }}
            </li>
          </ul>
          <div class="card-spacer" />
          <div class="card-price" v-if="card.price">{{ card.price }}</div>
        </div>
      </el-card>
    </el-col>
  </el-row>

  
  </section>
</template>

<script setup>
const cards = [
  {
    title: "Сервис по ремонту авто",
    features: ["10 сотрудников", "медицинский осмотр", "заключительная документация"],
    price: "~ 50 000 руб.",
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#2A2A2A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M3 17v-6a4 4 0 0 1 8 0v6"/>
      <rect x="1" y="17" width="20" height="5" rx="2" ry="2"/>
      <path d="M16 17v-3a4 4 0 0 1 8 0v3"/>
    </svg>`,
  },
  {
    title: "Аграрный комплекс",
    features: ["200 сотрудников", "медицинский осмотр", "консультации специалистов"],
    price: "~ 500 000 руб.",
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#2A2A2A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <circle cx="12" cy="12" r="10"/>
      <path d="M8 12l2 2 4-4"/>
    </svg>`,
  },
  {
    title: "Промышленный гигант",
    features: [
      "1000 сотрудников",
      "медицинский осмотр",
      "система динамического наблюдения",
      "сеть здравпунктов",
    ],
    price: "~ 5 000 000 руб.",
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#2A2A2A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M3 12h18"/>
      <path d="M3 6h18"/>
      <path d="M3 18h18"/>
    </svg>`,
  },
  {
    title: "Узнать стоимость услуг для вашего бизнеса",
    features: [],
    price: "",
    icon: `<svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="#2A2A2A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <circle cx="12" cy="12" r="10"/>
      <path d="M12 6v6l4 2"/>
    </svg>`,
  },
]
</script>

<style scoped>

.cards-container {
  margin-top: 40px;
  max-width: 1200px;
  margin-left: auto;
  margin-right: auto;
}

.card-column {
  display: flex;
}

.card {
  display: flex;
  flex: 1;
  flex-direction: column;
  border-radius: 12px;
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.06);
  transition: box-shadow 0.3s ease;
  height: 100%;
}

.card:hover {
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.12);
}

.card-content {
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  padding: 32px 24px;
}

.icon {
  margin-bottom: 20px;
  width: 48px;
  height: 48px;
  align-self: center;
}

.card-title {
  font-weight: 700;
  font-size: 1.25rem;
  line-height: 1.4;
  color: #2a2a2a;
  text-align: center;
  margin-bottom: 18px;
  min-height: 56px;
}

.card-list {
  list-style: none;
  padding: 0;
  margin: 0;
  color: #555;
  font-size: 0.95rem;
  line-height: 1.5;
  text-align: center;
  margin-bottom: 20px;
}

.card-list-item {
  margin-bottom: 8px;
}

.card-spacer {
  flex-grow: 1;
}

.card-price {
  font-weight: 700;
  font-size: 1.1rem;
  color: #ff7f50;
  text-align: center;
  margin-top: auto;
}

  .title {
    font-size: 1.3rem;
    font-weight: 700;
    margin-bottom: 14px;
    color: #222;
  }

  .info-list {
    list-style: none;
    padding: 0;
    margin: 0 0 18px 0;
    color: #555;
    font-size: 0.95rem;
    line-height: 1.5;
  }

  .info-list li {
    margin-bottom: 8px;
  }

  .price {
    font-weight: 700;
    font-size: 1.1rem;
    color: #117a8b; /* приятный синий */
  }

  /* Последняя карточка с другим стилем */
  .card.special {
    background: #117a8b;
    color: #fff;
    text-align: center;
    cursor: pointer;
  }

  .card.special .title {
    font-size: 1.4rem;
  }

  .card.special:hover {
    background: #0e5d66;
  }



.why-title{
        padding-left: 10%;
    font-size: 57px;
    font-weight: bold;
    margin-bottom: 24px;
    color: black;
    position: relative;
    background: white;
    z-index: 20;
}

.founder-card.reverse {
  flex-direction: row-reverse;
}

/* Мобильная версия — всегда вертикально, без реверса */


.founders-section {
  display: flex;
  flex-direction: column;
  gap: 60px;
  padding: 60px 20px;
  font-family: sans-serif;
}

.founder-card {
  display: flex;
  justify-content: space-between;

  align-items: center;
  gap: 20px;
}

.founder-card.light {
  background: #fff;
  color: #000;
  height: 40vh;
}

.founder-card.dark {
  background: #1e1e1e;
  color: #fff;
  padding: 40px 67px;

  height: 40vh;
}

.founder-card .left,
.founder-card .right {
  flex: 1 1 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.left {
  flex-direction: column;
  text-align: center;
}

.right p,
.left p {
  font-size: 54px;
  line-height: 1.6;
  max-width: 100%;
  text-indent: 4%;
}



.name {
  font-weight: bold;
  text-transform: lowercase;
}

.title {
  font-size: 14px;
  color: #888;
}

.link {
  color: #0070f3;
  font-weight: 600;
  text-decoration: none;
}


@media (max-width: 768px) { 

.right p{
    font-size: 18px;
    max-width: 100%;
        text-indent: 0%;
}
.founder-card{
  display: block;
}
.why-title {
    padding-left: 0;
    font-size: 27px;
    font-weight: bold;
    margin-bottom: 24px;
    color: black;
    position: relative;
    background: white;
    z-index: 20;
    margin: 0;
}
.founders-section{
  gap: 0;
}
.founder-card {
  height: auto !important;
}

}



</style>
