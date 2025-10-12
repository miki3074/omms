<template>
  <section class="about-section">
    <div class="about-content">
      <!-- <h2 class="about-title">О компании</h2> -->
      <p class="about-text">
        <strong>ООО НПО "Объединенные Медицинские Системы"</strong> – медицинская организация, возглавляемая командой профессионалов с обширным опытом организации комплексных программ оздоровления для промышленных предприятий.
      </p>
      <p class="about-text">
        Главная ценность нашей компании – это исчерпывающее удовлетворение потребностей заказчиков. Мы развиваем <strong>оперативность</strong> – как навык, и культивируем <strong>умение нестандартно мыслить</strong> – как жизненную необходимость в меняющемся мире.
      </p>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  background-color: #ffffff;
  padding: 60px 5vw;
  font-family: 'Helvetica Neue', sans-serif;
  color: #2a2a2a;
}

.about-title {
  font-size: clamp(28px, 5vw, 48px);
  font-weight: 700;
  color: #0d72b9;
  margin-bottom: 30px;
  text-align: left;
}

.about-text {
  font-size: clamp(16px, 2vw, 20px);
  line-height: 1.6;
  margin-bottom: 20px;
  text-align: left;
}

@media (max-width: 768px) {
  .about-title {
    text-align: center;
  }
  .about-text {
    text-align: justify;
  }
}
</style>
