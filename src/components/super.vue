<script setup lang="ts">

</script>

<template>
  <section class="founders-section">
    <h2 class="why-title">суперкоманда</h2>
    <div class="founder-card light">
      <div class="left"></div>
      <div class="right">
        
        <p>
          Группа компаний «Региональный центр профпатологии» – настоящие профессионалы. Мы постоянно повышаем свою квалификацию, изучаем новости законодательства, обмениваемся друг с другом опытом и знаниями – и каждый день стараемся стать лучше, чем вчера.
        </p>
      </div>
    </div>

   
  </section>
</template>

<style scoped>
.founders-section {
  padding: 60px 5vw;
  font-family: sans-serif;
  background: #fff;
}

.why-title {
  font-size: clamp(28px, 6vw, 57px);
  font-weight: bold;
  margin-bottom: 24px;
  color: black;
}

.founder-card {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  margin-bottom: 40px;
}

.right p {
  font-size: clamp(18px, 4vw, 54px);
  line-height: 1.6;
   margin-left: clamp(0px, 5vw, 19%);
}

.link {
  color: #0070f3;
  font-weight: 600;
}

.cards-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.card {
  background: white;
  border-radius: 12px;
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.06);
  transition: box-shadow 0.3s ease;
  display: flex;
  flex-direction: column;
  padding: 32px 24px;
}

.card:hover {
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.12);
}

.card-title {
  font-size: clamp(18px, 2vw, 24px);
  font-weight: 700;
  text-align: center;
  margin-bottom: 18px;
}

.card-list {
  list-style: none;
  padding: 0;
  font-size: clamp(14px, 1.6vw, 16px);
  text-align: center;
  margin-bottom: 20px;
}

.card-list-item {
  margin-bottom: 8px;
}

.card-price {
  font-size: clamp(16px, 2vw, 20px);
  font-weight: 700;
  color: #ff7f50;
  text-align: center;
}

.icon {
  width: 48px;
  height: 48px;
  margin: 0 auto 20px auto;
}
</style>
