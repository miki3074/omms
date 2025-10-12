<template>
  <section class="advantages-section">
    <h2 class="advantages-title">Наши преимущества</h2>
    <div class="advantages-grid">
      <div class="advantage-item">
        <div class="emoji">🛡️</div>
        <h3 class="advantage-title">Юридическая гарантия</h3>
        <p class="advantage-text">
          Все заключения соответствуют требованиям Роспотребнадзора и трудового законодательства.
        </p>
      </div>
      <div class="advantage-item">
        <div class="emoji">⏱️</div>
        <h3 class="advantage-title">Сроки "под ключ"</h3>
        <p class="advantage-text">
          От составления списка работников до сдачи отчетности в контролирующие органы.
        </p>
      </div>
      <div class="advantage-item">
        <div class="emoji">📊</div>
        <h3 class="advantage-title">Индивидуальный подход</h3>
        <p class="advantage-text">
          Учет специфики вашего производства и особенностей закупочных процедур.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.advantages-section {
  padding: 60px 5vw;
  background-color: #f9f9f9;
  font-family: 'Helvetica Neue', sans-serif;
}

.advantages-title {
  font-size: clamp(28px, 5vw, 48px);
  font-weight: bold;


  margin-bottom: 40px;
}

.advantages-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 30px;
}

.advantage-item {
  background: #fff;
  padding: 30px 20px;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.advantage-item:hover {
  transform: translateY(-4px);
}

.emoji {
  font-size: 40px;
  margin-bottom: 16px;
}

.advantage-title {
  font-size: 20px;
  font-weight: 700;
  color: #222;
  margin-bottom: 10px;
}

.advantage-text {
  font-size: 16px;
  line-height: 1.5;
  color: #555;
}
</style>
