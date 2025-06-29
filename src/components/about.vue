<script setup lang="ts">
// Ничего не нужно в логике
</script>

<template>
  <section class="founders-section">
    <!-- Первый блок -->
    <div class="founder-card light">
      <div class="left">
        <img class="avatar" src="@/assets/dir.jpg" alt="Ильсур Исламов" />
        <div class="info">
          Ильсур Исламов<br />
          генеральный директор
        </div>
      </div>
      <div class="right">
        <p>
          <span class="link">мы — профессионалы.</span> Наш опыт – организация эффективных медицинских программ для работников и предприятий. Мы быстро и нестандартно мыслим, чтобы сделать медицинскую помощь доступной и качественной.
        </p>
      </div>
    </div>

    <!-- Второй блок -->
    <div class="founder-card dark reverse">
      <div class="left">
        <!-- Показывается только на ПК -->
        <img class="photo photopk" src="@/assets/doc.webp" alt="Степанов Роберт" />
        <!-- Показывается только на мобилке -->
        <p class="textmob">
          мы умеем работать как с крупными промышленными предприятиями, так и с небольшими частными компаниями, медицинскими организациями и многими другими сферами.
          <br /><br />
          <span class="name">Степанов Роберт</span><br />
          главный врач
        </p>
      </div>
      <div class="right">
        <!-- Показывается только на ПК -->
        <p class="textpk">
          мы умеем работать как с крупными промышленными предприятиями, так и с небольшими частными компаниями, медицинскими организациями и многими другими сферами.
        </p>
        <!-- Показывается только на мобилке -->
        <img class="photo photomob" src="@/assets/doc.webp" alt="Степанов Роберт" />
      
        
      </div>
    </div>
  </section>
</template>

<style scoped>
.founders-section {
  display: flex;
  flex-direction: column;
  gap: 60px;
  padding: 60px 20px;
  font-family: sans-serif;
}

/* Общий стиль карточек */
.founder-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  padding: 40px 60px;
  border-radius: 12px;
}

.founder-card.light {
  background: #fff;
  color: #000;
}

.founder-card.dark {
  background: #1e1e1e;
  color: #fff;
}

.founder-card.reverse {
  flex-direction: row-reverse;
}

.left,
.right {
  flex: 1 1 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.left {
  flex-direction: column;
  text-align: center;
}

.avatar {
  max-width: 72px;
  border-radius: 13%;
  object-fit: cover;
  margin-bottom: 12px;
}

.photo {
  max-width: 300px;
  border-radius: 10px;
}

.info {
  font-size: 16px;
  color: #666;
  margin-top: 8px;
}

.right p,
.left p {
  font-size: clamp(18px, 2.5vw, 32px); 
  line-height: 1.5;
  text-indent: 4%;
}

.link {
  color: #0070f3;
  font-weight: 600;
  text-decoration: none;
}

.name {
  font-weight: bold;
  color: #fff;
}

.textmob {
  display: none;
}

.textpk {
  display: block;
}

.photomob {
  display: none;
}

.photopk {
  display: block;
}

/* ✅ Мобильная адаптация */
@media (max-width: 768px) {
  .founder-card {
    flex-direction: column;
    text-align: left;
    padding: 20px;
    display: block;
  }

  .left,
  .right {
    flex: 1 1 100%;
    justify-content: flex-start;
    align-items: flex-start;
  }

  .avatar,
  .photo {
    max-width: 120px;
    margin-bottom: 10px;
  }

  .right p,
  .left p {
    font-size: 18px;
    text-indent: 0;
            text-align: left;
  }

.left p{
   text-indent: 9%;
}

  .textmob {
    display: block;
    font-size: 18px;
    line-height: 1.6;
  }

  .textpk {
    display: none;
  }

  .photomob {
    display: block;
    border-radius: 10px;
    margin-top: 20px;
  }

  .photopk {
    display: none;
  }

  .info {
    font-size: 14px;
    text-align: left;
    color: #999;
  }

  .founders-section {
    gap: 30px;
    padding: 20px;
  }
}
</style>
