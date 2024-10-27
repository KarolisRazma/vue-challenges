<script setup lang="ts">
import FaqSectionListItem from './FaqSectionListItem.vue'

interface Question {
  question: string
  answer: string
  open: boolean
}

const props = defineProps<{
  questions: Question[]
}>()
</script>

<template>
  <FaqSectionListItem
    v-for="{ question, answer, open } in props.questions"
    :key="question"
    :question
    :answer
    :is-default-active="open"
  />
</template>
