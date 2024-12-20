<template>
  <div class="experience-card">
    <h3 class="title">{{ title }}</h3>
    <p class="company">{{ company }}</p>
    <p class="dates">
      {{ formatDate(startDate) }} - {{ endDate ? formatDate(endDate) : 'Present' }}
    </p>
    <ul class="description">
      <li v-for="(item, index) in description" :key="index">
        {{ item }}
      </li>
    </ul>
    <div class="technologies">
      <span v-for="tech in technologies" :key="tech" class="technology">
        {{ tech }}
      </span>
    </div>
  </div>
</template>

<script setup lang="ts">
import dayjs from 'dayjs'

interface Props {
  title: string
  company: string
  startDate: string
  endDate?: string
  description: string[]
  technologies: string[]
}

defineProps<Props>()

const formatDate = (date: string) => {
  return dayjs(date).format('MMM YYYY')
}
</script>

<style lang="scss" scoped>

</style>
