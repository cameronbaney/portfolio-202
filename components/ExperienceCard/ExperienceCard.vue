<template>
  <div>
    <div class="mb-6 sm:mb-0">
      <div>
        <h3>{{ experience.company }}</h3>
        <div class="mb-4">
        <p class="mb-2 italic" v-for="position in experience.positions" :key="position.title">{{ position.title }} | {{ dateRange(position.dateStarted, position.dateEnded) }}</p>
        </div>
      </div>
    </div>
    <ul>
      <li
        v-for="bullet in experience.bullets"
        :key="bullet"
      >
        {{ bullet }}
      </li>
    </ul>

  </div>
</template>

<script lang="ts">
import Vue, { PropOptions } from 'vue'

import dayjs from 'dayjs'

interface Position {
  title: string,
  dateStarted: string,
  dateEnded: string
}

interface Experience {
  title: string,
  company: string,
  description: string,
  dateStarted: string,
  dateEnded: string,
  positions: Array<Position>
}

export default Vue.extend({
  name: 'ExperienceCard',

  props: {
    experience: {
      type: Object,
      required: true
    } as PropOptions<Experience>
  },

  methods: {
    /**
     * Compute date range
     */
    dateRange(dateStarted: string, dateEnded: string): string {
      const startDate = dayjs(dateStarted).format('MMMM YYYY')

      const endDate = dateEnded
        ? dayjs(dateEnded).format('MMMM YYYY')
        : 'Present'

        return `${startDate} - ${endDate}`
    }
  }
})
</script>

<style lang="scss" scoped>

</style>
