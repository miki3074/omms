<script setup lang="ts">
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const phone = ref('')
const consent = ref(false)

const handleSubmit = () => {
  if (!consent.value) {
    alert('Пожалуйста, подтвердите согласие на обработку ПД.')
    return
  }

  // Тут будет отправка данных
  console.log('Отправка:', { name: name.value, email: email.value, phone: phone.value })
  alert('Форма отправлена!')
}
</script>

<template>
  <section class="contact-section" id="fot">
    <div class="contact-container">
      <div class="contact-left">
        <h1>нужна помощь?<br />обращайтесь!</h1>
      </div>
      <div class="contact-right">
        <form @submit.prevent="handleSubmit" class="form">
          <input v-model="name" type="text" placeholder="имя" required />
          <input v-model="email" type="email" placeholder="электропочта" required />
          <input v-model="phone" type="tel" placeholder="телефон" required />

          <label class="consent">
            <input type="checkbox" v-model="consent" />
            <span>
              Я даю согласие на обработку ПД и согласен с
              <a href="#" target="_blank">Политикой обработки персональных данных</a>
            </span>
          </label>

          <button type="submit">отправить</button>
        </form>

      
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-section {
  height: 100vh;
  background: linear-gradient(135deg, #006eff, #347cff);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 40px 20px;
}

.contact-container {
  display: block;
  justify-content: space-between;
  gap: 40px;
  width: 100%;
  max-width: 1200px;
  flex-wrap: wrap;
}

.contact-left {
  flex: 1 1 50%;
}

.contact-left h1 {
     font-size: 130px;
    font-weight: bold;
    line-height: 1.2;
    position: relative;
    top: 105px;
    left: 2%;

}

.contact-right {
  flex: 1 1 40%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

input[type='text'],
input[type='email'],
input[type='tel'] {
  background: transparent;
  border: none;
  border-bottom: 1px solid white;
  color: white;
  font-size: 37px;
  padding: 10px 0;
  outline: none;
}

::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.consent {
  font-size: 12px;
  display: flex;
  gap: 8px;
  align-items: flex-start;
  color: white;
}

.consent input {
  margin-top: 4px;
}

.consent a {
  color: white;
  text-decoration: underline;
}

button[type='submit'] {
  margin-top: 20px;
  padding: 16px;
  font-size: 18px;
  background-color: black;
  color: white;
  border: none;
  border-radius: 40px;
  cursor: pointer;
  width: 100%;
}

.footer {
  margin-top: 30px;
  font-size: 12px;
  display: flex;
  justify-content: space-between;
  color: white;
  flex-wrap: wrap;
  gap: 10px;
}

/* Responsive */
@media (max-width: 768px) {
  .contact-container {
    flex-direction: column;
    align-items: flex-start;
  }

  .contact-left h1 {
    font-size: 42px;
  }

  .footer {
    flex-direction: column;
    align-items: flex-start;
    font-size: 11px;
  }

  .contact-left h1{
    top: 0;
    left: 0;
  }
  
input[type='text'],
input[type='email'],
input[type='tel'] {
    font-size: 19px;
}

}
</style>
