<template>
  <div>
    <h1 class="text-4xl sm:text-5xl font-bold mb-0">Cameron Baney</h1>
    <h2 class="text-2xl sm:text-3xl font-semibold mb-8">Front-end Engineer</h2>
    <p class="text-lg sm:text-xl mb-8">I am a frontend engineer focusing on JavaScript, React, Sass and semantic HTML. My experience in design and UX helps create quality user friendly websites and software.</p>
    <p class="text-lg sm:text-xl mb-8">Developer at <a href="https://shopify.engineering/">Shopify</a> building <a href="https://www.shopify.com/inbox">Inbox</a>.</p>
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
          link: 'https://linkedin.com/in',
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
