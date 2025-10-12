<script setup lang="ts">
// логика не нужна
</script>

<template>
  <section class="founders-section">
    <div class="founder-card dark" style="background-color: #212121;">
      <div class="left">
        <!-- 💬 Текст для ПК -->
        <p class="textpk">
          наш подход сочетает системность и человечность. Мы работаем прозрачно,
          действуем на опережение и тщательно контролируем каждый этап.
          При этом сохраняем искреннюю вовлеченность и по-настоящему заинтересованы
          в успехе каждого заказчика.
        </p>

        <!-- 💬 Текст для мобилы -->
        <p class="textmob">
          наш подход сочетает системность и человечность. Мы работаем прозрачно,
          действуем на опережение и тщательно контролируем каждый этап.
          При этом сохраняем искреннюю вовлеченность и по-настоящему заинтересованы
          в успехе каждого заказчика.

          <br /><br />
          <span class="name">Ильсур Исламов</span><br />
          генеральный директор
        </p>
      </div>

      <div class="right">
        <img class="photo photopk" src="@/assets/qqqq.png" alt="Ильсур Исламов" />
        <img class="photo photomob" src="@/assets/qqqq.png" alt="Ильсур Исламов" />
      </div>
    </div>
  </section>
</template>

<style scoped>
/* === Общий стиль секции === */
.founders-section {
  display: flex;
  flex-direction: column;
  gap: 60px;
  padding: 60px 20px;
  font-family: sans-serif;
  background: #fff;
}

/* === Карточка === */
.founder-card {
  display: flex;
  justify-content: space-between;
  align-items: stretch;
  gap: 20px;
  padding: 0 60px;
  position: relative;
  overflow: hidden;
  min-height: 600px;
  border-radius: 16px;
}

.founder-card.dark {
  background: #1e1e1e;
  color: #fff;
}

/* === Левая часть (текст) === */
.left {
  flex: 1 1 50%;
  display: flex;
  align-items: center;
  justify-content: flex-start;
}

.right p,
.left p {
  font-size: clamp(18px, 2.5vw, 46px);
  line-height: 1.4;
  text-indent: 4%;
  
}

.textmob {
  display: none;
}

.textpk {
  display: block;
}

/* === Правая часть (фото) === */
.right {
  flex: 1 1 50%;
  display: flex;
  align-items: flex-end; /* 📍 фото прижато к низу */
  justify-content: center;
  position: relative;
  overflow: hidden;
}

/* === Фото === */
.photo {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: auto;
  max-width: none;
  height: 100%;
  object-fit: contain;
}

.photopk {
  display: block;
}

.photomob {
  display: none;
}

.name {
  font-weight: bold;
  color: #fff;
}

/* === Мобильная адаптация === */
@media (max-width: 768px) {
  .founder-card {
    flex-direction: column;
    padding: 20px;
    min-height: auto;
  }

  .left,
  .right {
    flex: 1 1 100%;
    position: static;
    align-items: flex-start;
  }

  .photopk {
    display: none;
  }

  .photomob {
    display: block;
    position: relative;
    width: 63%;
    height: auto;
    border-radius: 10px;
    margin-top: 20px;
  }

  .textpk {
    display: none;
  }

  .textmob {
    display: block;
    font-size: 18px;
    line-height: 1.6;
  }

  .right p,
  .left p {
    font-size: 18px;
    text-indent: 0;
    text-align: left;
  }

  .founders-section {
    gap: 30px;
    padding: 20px;
  }
}
</style>
