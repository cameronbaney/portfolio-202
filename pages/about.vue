<template>
  <div>
    <h1>About</h1>

    <h2>Experience</h2>
    <div class="mb-24">
      <experience-card
        class="mb-16"
        v-for="item in experience"
        :key="item.company"
        :experience="item"
      />
    </div>

    <h2>Education</h2>
    <nuxt-content class="mb-24" :document="education" />

    <h2>Interests</h2>
    <nuxt-content class="mb-24" :document="interests" />

    <h2>Skills</h2>
    <nuxt-content class="mb-24" :document="skills" />
  </div>
</template>

<script>
export default {
  name: 'PageAbout',

  async asyncData({ $content }) {
    const interests = await $content('interests')
      .fetch()

    const skills = await $content('skills')
      .fetch()

    const education = await $content('education')
      .fetch()

    const experience = await $content('experience')
      .sortBy('dateStarted', 'desc')
      .fetch()

    return {
      interests,
      skills,
      education,
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
