<template>
  <section class="cta-section">
    <div class="cta-container">
      <div class="cta-text">
        <h2 class="cta-title zagol">Остались вопросы?</h2>
        <p class="cta-subtitle textt">
          Наш специалист проконсультирует вас по:
        </p>

        <ul class="cta-list">
          <li class="textt">▸ перечню необходимых осмотров</li>
          <li class="textt">▸ требованиям к опасным производствам</li>
          <li class="textt">▸ стоимости услуг для вашего предприятия</li>
        </ul>

        <p class="cta-email">
          <a href="mailto:info@rcpprt.ru" class="textt">info@rcpprt.ru</a>
        </p>

        <a href="#contact" class="cta-button textt">связаться</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cta-section {

  color: #000000;
  padding: 100px 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: left;
  font-family: "Helvetica Neue", Arial, sans-serif;
}

.cta-container {
  width: 100%;
  max-width: 1200px;
  background: rgba(255, 255, 255, 0.08);
  border-radius: 24px;
  padding: 60px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.2);
  backdrop-filter: blur(8px);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.cta-container:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 28px rgba(0, 0, 0, 0.3);
}

.cta-title {
  font-size: clamp(32px, 5vw, 64px);
  font-weight: 700;
  margin-bottom: 20px;
}

.cta-subtitle {
  font-size: clamp(18px, 2.5vw, 24px);
  margin-bottom: 20px;
  color: #000000;
}

.cta-list {
  list-style: none;
  padding: 0;
  margin-bottom: 30px;
  font-size: clamp(16px, 2vw, 20px);
  color: #000000;
}

.cta-list li {
  margin-bottom: 10px;
  line-height: 1.4;
}

.cta-email {
  font-size: clamp(16px, 2vw, 20px);
  margin-bottom: 40px;
}

.cta-email a {
  color: #000000;
  text-decoration: underline;
  transition: opacity 0.3s ease;
}

.cta-email a:hover {
  opacity: 0.8;
}

.cta-button {
  display: inline-block;
  background: #001aff;
  color: #ffffff;
  font-size: clamp(18px, 2.5vw, 28px);
  padding: 16px 48px;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  box-shadow: 0 4px 10px rgba(255, 255, 255, 0.25);
}

.cta-button:hover {
  background: #e6e6e6;
  transform: translateY(-3px);
}

/* 📱 Мобильная адаптация */
@media (max-width: 768px) {
  .cta-section {
    padding: 60px 20px;
    text-align: center;
  }

  .cta-container {
    padding: 40px 24px;
  }

  .cta-title {
    font-size: 36px;
  }

  .cta-subtitle {
    font-size: 18px;
  }

  .cta-list {
    text-align: left;
    display: inline-block;
  }

  .cta-button {
    width: auto;
    padding: 14px 36px;
    font-size: 20px;
  }
}
</style>
