<template>
  <div>
    <h1 class="mb-12">Experience</h1>
    <experience-card class="mb-24" v-for="item in experience" :key="item.company" :experience="item" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const experience = await $content('experience')
      .sortBy('dateStarted', 'desc')
      .fetch()

    return {
      experience
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
