<template>
  <div class="page-blog">
    <h1>Blog</h1>

    <blog-post
      v-for="post in posts"
      :key="post.slug"
      :post="post"
    />
  </div>
</template>

<script>
import dayjs from 'dayjs'

export default {
  name: 'Blog',

  async asyncData({ $content, params }) {
    const posts = await $content(`blog`)
      .only(['title', 'description', 'createdAt', 'slug', 'path'])
      .fetch()

    return {
      posts
    }
  },

  head() {
    return {
      title: 'Blog'
    }
  },

  methods: {
    /**
     * Compute date published
     * @returns {String}
     */
    // datePublished: function(date) {
    // }
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
