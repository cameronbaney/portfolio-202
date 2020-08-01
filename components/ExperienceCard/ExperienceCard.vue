<template>
  <div>
    <div class="flex flex-col sm:flex-row mb-6 sm:mb-0 justify-between">
      <div>
        <h2 class="text-2xl font-bold mb-2">{{ experience.title }}</h2>
        <h3 class="text-xl mb-4">{{ experience.company }}</h3>
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
