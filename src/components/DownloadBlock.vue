<template>
  <section class="docs-section">
    <h2>Скачать документы</h2>
    <ul class="docs-list">
      <li v-for="(doc, index) in docs" :key="index">
        <a :href="doc.path" :download="doc.name">
          📄 {{ doc.name }}
        </a>
      </li>
    </ul>
    Вставить другие доки
  </section>
</template>

<script setup>


import presentation from '@/assets/docs/ob-ohrane-zdorovya.pdf'

const docs = [


  { name: 'Презентация (PDF)', path: presentation },
]
</script>

<style scoped>
.docs-section {
  padding: 40px;
  background: #f5f5f5;
  border-radius: 12px;
  max-width: 800px;
  margin: auto;
}

.docs-section h2 {
  font-size: 32px;
  margin-bottom: 20px;
  color: #333;
}

.docs-list {
  list-style: none;
  padding: 0;
}

.docs-list li {
  margin-bottom: 12px;
}

.docs-list a {
  text-decoration: none;
  font-size: 20px;
  color: #0050ff;
  transition: color 0.2s ease;
}

.docs-list a:hover {
  color: #003bcc;
}
</style>
