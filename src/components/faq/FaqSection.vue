<script setup lang="ts">
import FaqSectionList from '@/components/faq/FaqSectionList.vue'
import { questions } from './questions'
</script>
<template>
  <div class="faq-section">
    <div class="faq-section-header">Frequently asked questions</div>
    <FaqSectionList :questions />
  </div>
</template>

<style scoped>
.faq-section-header {
  text-align: center;
  font-weight: bold;
  font-size: 32px;
  padding: 5px;
  margin-bottom: 10px;
}

.faq-section {
  max-width: 800px;
  margin: 0 auto;
  border: 1px black solid;
  padding: 10px;
  margin-top: 30px;
}
</style>
