<script setup lang="ts">

</script>

<template>
  <section class="founders-section">
    <h2 class="why-title">суперкоманда</h2>
    <!-- Первый блок -->
    <div class="founder-card light">
      <div class="left" style="    flex: 1 1 1%;">
      
      </div>
      <div class="right">
        <p>

       Группа компаний «Региональный центр профпатологии» – настоящие профессионалы. Мы постоянно повышаем свою квалификацию, изучаем новости законодательства, обмениваемся друг с другом опытом и знаниями – и каждый день стараемся стать лучше, чем вчера.
        </p>
      </div>
    </div>

  



  
  </section>
</template>



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
  height: auto !important;
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
}


</style>
