<template>
  <footer class="footer">
    <div class="footer-container">
      <!-- Левая часть — реквизиты -->
      <div class="footer-info">
        <h2 class="footer-title zagol">Реквизиты</h2>
        <p class="textt">
          <strong class="textt">Общество с ограниченной ответственностью<br />
          Научно-производственное объединение<br />
          «Объединенные медицинские системы» (ООО НПО «ОМС»)</strong>
        </p>

        <p class="textt">
          <strong class="textt">Юридический адрес:</strong><br />
          423831, Республика Татарстан, г. Набережные Челны,<br />
          ул. Шамиля Усманова, д. 63, офис 208в.
        </p>

        <p class="textt">
          <strong class="textt">Адрес центрального офиса:</strong><br />
          420111, Республика Татарстан, г. Казань,<br />
          ул. Пушкина, д. 12, офис 404.
        </p>

        <p class="textt">
          <strong class="textt">Почтовый адрес:</strong><br />
          420132, Республика Татарстан, г. Казань, а/я 42.
        </p>

        <p class="textt">
          <strong class="textt">ОГРН:</strong> 1201600094190<br />
          <strong class="textt">ИНН:</strong> 1650397806<br />
          <strong class="textt">КПП:</strong> 165001001
        </p>
      </div>

      <!-- Правая часть — карта -->
      <div class="footer-map">
        <iframe
          src="https://yandex.ru/map-widget/v1/?um=constructor%3A2c35b0a87fa75b1d3df3cf8cc43bbd22e12d651a11684fd0a1951d9878d07a87&amp;source=constructor"
          width="100%"
          height="100%"
          frameborder="0"
          allowfullscreen
        ></iframe>
      </div>
    </div>

    <!-- Нижняя полоса -->
    <div class="footer-bottom zagol">
      © {{ new Date().getFullYear() }} ООО НПО «ОМС». Все права защищены.
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: #0d72b9;
  color: #fff;
  padding: 60px 5% 20px;
  font-family: "Helvetica Neue", Arial, sans-serif;
}

.footer-container {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 60px;
  align-items: start;
}

.footer-title {
  font-size: clamp(22px, 2vw, 32px);
  font-weight: 700;
  margin-bottom: 20px;
  color: #fff;
}

.footer-info p {
  font-size: clamp(14px, 1.2vw, 18px);
  line-height: 1.6;
  margin: 10px 0;
  color: #f2f2f2;
}

.footer-info strong {
  color: #ffffff;
  font-weight: 600;
}

.footer-map {
  width: 100%;
  height: 400px;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.3);
}

/* Нижняя часть */
.footer-bottom {
  text-align: center;
  padding-top: 30px;
  border-top: 1px solid rgba(255, 255, 255, 0.2);
  margin-top: 40px;
  font-size: 14px;
  color: #e0e0e0;
}

/* 📱 Адаптив */
@media (max-width: 1024px) {
  .footer-container {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .footer-map {
    height: 300px;
  }

  .footer-info {
    text-align: center;
  }

  .footer-info p {
    font-size: 16px;
  }
}

@media (max-width: 600px) {
  .footer {
    padding: 40px 20px 20px;
  }

  .footer-map {
    height: 250px;
  }

  .footer-bottom {
    font-size: 12px;
  }
}
</style>
