<script setup lang="ts">
import { onBeforeMount, ref } from 'vue'

const isActive = ref<boolean>(false)

const props = defineProps<{
  question: string
  answer: string
  isDefaultActive: boolean
}>()

const toggleActive = () => {
  isActive.value = !isActive.value
}

onBeforeMount(() => {
  isActive.value = props.isDefaultActive
})
</script>

<template>
  <div class="faq-item" :class="{ active: isActive }" @click="toggleActive">
    <div class="faq-item-question">
      {{ props.question }}
    </div>
    <div v-if="isActive" class="faq-item-answer">{{ props.answer }}</div>
  </div>
</template>

<style scoped>
.faq-item {
  border: 1px black solid;
  padding: 10px;
  cursor: pointer;
  width: 75%;
  margin: 10px auto;
}

.faq-item.active .faq-item-question::before {
  transform: rotate(90deg);
}

.faq-item-question::before {
  content: '▶';
  display: inline-block;
  margin-right: 8px;
  transition: transform 0.2s;
}

.faq-item-question {
  font-weight: bold;
  padding: 5px;
}

.faq-item-answer {
  padding: 5px;
  font-weight: 400;
}
</style>
