<template>
  <div>
    <h1 class="text-4xl sm:text-5xl font-bold mb-0">Cameron Baney</h1>
    <h2 class="text-2xl sm:text-3xl font-semibold mb-8">Senior Frontend Engineer</h2>
    <p class="text-lg sm:text-xl mb-8">Senior Frontend Engineer with over 10 years experience, specializing in JavaScript/TypeScript, React, and Vue.</p>
    <p class="text-lg sm:text-xl mb-8">Developer at <a href="https://shopify.engineering/">Shopify</a> building <a href="https://shopify.dev/docs/apps/checkout">Checkout Extensibility</a>.</p>
    <ul class="flex flex-row">
      <li class="mx-4 sm:mx-6 first:ml-0 last:mr-0" v-for="item in social" :key="item.link">
        <a class="h-8 sm:h-12 w-8 sm:w-12 block" :href="item.link" :title="item.title">
          <font-awesome-icon class="font-awesome-icon" :icon="['fab', item.icon]" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Homepage',

  data: function() {
    return {
      social: [
        {
          link: 'https://twitter.com/cameronbaney',
          icon: 'twitter',
          title: 'Twitter'
        },
        {
          link: 'https://github.com/cameronbaney',
          icon: 'github',
          title: 'GitHub'
        },
        {
          link: 'https://gitlab.com/cbaney',
          icon: 'gitlab',
          title: 'Gitlab'
        },
        {
          link: 'https://www.linkedin.com/in/cameronbaney',
          icon: 'linkedin',
          title: 'LinkedIn'
        },
        {
          link: 'https://codepen.io/cameronbaney',
          icon: 'codepen',
          title: 'CodePen'
        }
      ]
    }
  }
}
</script>

<style>

</style>
