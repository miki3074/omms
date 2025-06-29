<template>
  <footer class="site-footer">
    <div class="footer-container">
      <h2 class="footer-title">Реквизиты</h2>
      <p>Общество с ограниченной ответственностью Научно-производственное объединение «Объединенные медицинские системы» (ООО НПО «ОМС»)</p>
      
      <div class="addresses">
        <div class="address-block">
          <h3>Юридический адрес:</h3>
          <p>423831, Республика Татарстан, г. Набережные Челны, ул. Шамиля Усманова, д. 63, офис 208в.</p>
        </div>
        <div class="address-block">
          <h3>Адрес центрального офиса:</h3>
          <p>420111, Республика Татарстан, г. Казань, ул. Пушкина, д. 12, офис 404.</p>
        </div>
        <div class="address-block">
          <h3>Почтовый адрес:</h3>
          <p>420132, Республика Татарстан, г. Казань, а/я 42.</p>
        </div>
      </div>

      <div class="ids">
        <p><strong>ОГРН:</strong> 1201600094190</p>
        <p><strong>ИНН:</strong> 1650397806</p>
        <p><strong>КПП:</strong> 165001001</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  background-color: #0d72b9;
  color: white;
  padding: 40px 20px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 16px;
  line-height: 1.5;
  text-align: center;
}

.footer-container {
  max-width: 900px;
  margin: 0 auto;
}

.footer-title {
  font-size: 28px;
  font-weight: 700;
  margin-bottom: 24px;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  text-shadow: 0 2px 6px rgba(0,0,0,0.3);
}

.addresses {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 24px;
  margin-bottom: 30px;
}

.address-block {
  flex: 1 1 280px;
  min-width: 250px;
  text-align: left;
}

.address-block h3 {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 6px;
  color: #cce4ff;
}

.ids {
  display: flex;
  justify-content: center;
  gap: 40px;
  flex-wrap: wrap;
  font-weight: 600;
}

.ids p {
  margin: 4px 0;
  min-width: 120px;
  text-align: left;
}

/* Адаптив для мобильных */
@media (max-width: 640px) {
  .addresses {
    flex-direction: column;
    gap: 20px;
  }

  .address-block {
    text-align: center;
    min-width: auto;
  }

  .ids {
    flex-direction: column;
    gap: 10px;
    font-size: 14px;
    text-align: center;
  }

  .ids p {
    min-width: auto;
  }
}
</style>
