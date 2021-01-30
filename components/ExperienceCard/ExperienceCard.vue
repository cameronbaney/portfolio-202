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
    <p>{{ experience.description}}</p>
  </div>
</template>

<script>
import dayjs from 'dayjs'

export default {
  name: 'ExperienceCard',

  props: {
    experience: {
      type: Object,
      default: () => {
        return {
          title: '',
          company: '',
          description: '',
          dateStarted: '',
          dateEnded: '',
          positions: []
        }
      }
    }
  },

  methods: {
    /**
     * Compute date range
     * @params {String} dateStarted
     * @params {String} dateEnded
     * @returns {String}
     */
    dateRange(dateStarted, dateEnded) {
      const startDate = dayjs(dateStarted).format('MMMM YYYY')

      const endDate = dateEnded
        ? dayjs(dateEnded).format('MMMM YYYY')
        : 'Present'

        return `${startDate} - ${endDate}`
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
