<template>
  <div :class="`page-blog page-${page.slug}`">
    <div class="mb-16">
      <h1 class="mb-2">{{ page.title }}</h1>
      <time :datetime="page.createdAt">{{ datePublished }}</time>
    </div>

    <nuxt-content :document="page" />
  </div>
</template>

<script>
import dayjs from 'dayjs'

export default {
  name: 'BlogPost',

  async asyncData({ $content, params }) {
    const page = await $content(`blog/${params.slug}` || 'index').fetch()

    return {
      page
    }
  },

  head() {
    return {
      title: this.page.title
    }
  },

  computed: {
    /**
     * Compute date published
     * @returns {String}
     */
    datePublished: function() {
      return dayjs(this.page.createdAt).format('MMMM D, YYYY')
    }
  }
}
</script>

<style>
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
