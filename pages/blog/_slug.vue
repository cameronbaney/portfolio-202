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
      title: this.page.title,
      meta: [
        {
          hid: 'og:title',
          name: 'og:title',
          content: this.page.title
        },
        {
          hid: 'og:type',
          name: 'og:type',
          content: 'article'
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: this.page.description
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: `https://cameronbaney.dev${this.page.path}`
        },
        {
          hid: 'og:site_name',
          name: 'og:site_name',
          content: `Cameron Baney - Front-end Engineer`
        },
        {
          hid: 'twitter:card',
          name: 'twitter:card',
          content: 'summary'
        },
        {
          hid: 'twitter:creator',
          name: 'twitter:creator',
          content: '@cameronbaney'
        },
        {
          hid: 'twitter:site',
          name: 'twitter:site',
          content: '@cameronbaney'
        }
      ]
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
