<template>
  <div class="site-header">
    <ul class="text-xl text-green-400 flex flex-row justify-between content-center">
      <li><nuxt-link to="index">Home</nuxt-link></li>
      <li><nuxt-link to="education">Education</nuxt-link></li>
      <li><nuxt-link to="interests">Interests</nuxt-link></li>
      <li><nuxt-link to="skills">Skills</nuxt-link></li>
      <li><nuxt-link to="uses">Uses</nuxt-link></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SiteHeader'
}
</script>
