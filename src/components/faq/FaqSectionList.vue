<script setup lang="ts">
import FaqSectionListItem from './FaqSectionListItem.vue'

interface Question {
  question: string
  answer: string
}

const props = defineProps<{
  questions: Question[]
}>()
</script>

<template>
  <FaqSectionListItem
    v-for="({ question, answer }, index) in props.questions"
    :key="question"
    :question
    :answer
    :is-default-active="index === 0"
  />
</template>
