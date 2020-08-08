<template>
  <div>
    <div class="flex flex-col sm:flex-row mb-6 sm:mb-0 justify-between">
      <div>
        <h3 class="mb-2">{{ experience.title }}</h3>
        <h4>{{ experience.company }}</h4>
      </div>
      <span class="pt-2">{{ date }}</span>
    </div>
    <p class="max-w-2xl">{{ experience.description}}</p>
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
          dateEnded: ''
        }
      }
    }
  },

  computed: {
    /**
     * Compute date employeed
     * @returns {String}
     */
    date: function() {
      const startDate = dayjs(this.experience.dateStarted).format('MMMM YYYY')

      const dateEnded = this.experience.dateEnded
        ? dayjs(this.experience.dateEnded).format('MMMM YYYY')
        : 'Present'

        return `${startDate} - ${dateEnded}`
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
