<template>
  <div>
    <h2 class="mb-2">
      <nuxt-link :to="post.path">{{ post.title }}</nuxt-link>
    </h2>
    <time class="mb-4 block" :datetime="post.createdAt">{{ date }}</time>

    <p>{{ post.description }}</p>


    <nuxt-link class="bg-green-400 hover:bg-green-200 focus:bg-green-200 text-gray-900 hover:text-gray-900 focus:text-gray-900 inline-block p-2 rounded" :to="post.path">Read post</nuxt-link>

  </div>
</template>

<script>
import dayjs from 'dayjs'

export default {
  name: 'BlogPost',

  props: {
    post: {
      type: Object,
      default: () => {
        return {
          createdAt: '',
          description: '',
          extensions: '',
          path: '',
          slug: '',
          title: ''
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
      return dayjs(this.post.createdAt).format('MMMM D, YYYY')
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
