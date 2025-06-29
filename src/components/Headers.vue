<script setup lang="ts">
const email = "info@rcpprt.ru"
</script>

<template>
  <header class="site-header">
    <div class="container">
      <!-- Левая часть: Название -->
      <div class="header-main">
        <div class="header-text">
          <h1>Группа компаний «Региональный центр профпатологии»</h1>
          <p class="sub">Медицинские осмотры для промышленных предприятий</p>
          <p class="sub">Управляющая компания: ООО НПО «ОМС»</p>
          <p class="sub small">
            Лицензия № Л041-01181-16/01187594 от 03.05.2024, выдана Минздравом РТ
          </p>
        </div>
        <!-- Правая часть: Контакты -->
        <div class="header-contact">
          <a :href="`mailto:${email}`" class="email">✉ {{ email }}</a>
          <button class="feedback-btn">Обратная связь</button>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.site-header {
background: linear-gradient(to right, #10181c, #084f92);
  color: white;
  padding: 30px 5%;
  font-family: sans-serif;
}

.container {
  max-width: 1300px;
  margin: 0 auto;
}

.header-main {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
  align-items: center;
}

.header-text h1 {
  font-size: 32px;
  margin-bottom: 10px;
  font-weight: 700;
}

.header-text .sub {
  font-size: 16px;
  margin-bottom: 4px;
}

.header-text .small {
  font-size: 14px;
  opacity: 0.9;
}

.header-contact {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 10px;
}

.email {
  color: #fff;
  text-decoration: none;
  font-size: 16px;
}

.feedback-btn {
  background: #e72d50;
  color: white;
  border: none;
  border-radius: 20px;
  padding: 10px 20px;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.3s ease;
}

.feedback-btn:hover {
  background: #c01f3f;
}

/* Адаптация */
@media (max-width: 768px) {
  .header-main {
    flex-direction: column;
    align-items: flex-start;
  }

  .header-contact {
    align-items: flex-start;
    margin-top: 10px;
  }

  .header-text h1 {
    font-size: 20px;
  }

  .header-text .sub {
    font-size: 14px;
  }

  .email {
    font-size: 14px;
  }

  .feedback-btn {
    padding: 8px 16px;
    font-size: 14px;
  }
}
</style>
