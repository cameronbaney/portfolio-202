<template>
  <div :class="`page-${page.slug}`">
    <h1>{{ page.title }}</h1>
    {{ page.description }}
    <nuxt-content :document="page" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const page = await $content(params.slug || 'index').fetch()

    return {
      page
    }
  },

  head() {
    return {
      title: this.page.title
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
