<template>
  <div>
    <h1 class="text-5xl font-bold mb-0">Cameron Baney</h1>
    <h2 class="text-3xl font-semibold mb-8">Front-end Engineer</h2>
    <p class="text-xl mb-8">I am a front-end engineer focusing on JavaScript, Vue, Sass and semantic HTML. My experience in design and UX helps create quality user friendly websites and software. Lead Engineer at <a href="https://blackfynn.com">Blackfynn.</a></p>
    <ul class="flex flex-row">
      <li class="mx-4 first:ml-0 last:mr-0" v-for="item in social" :key="item.link">
        <a :href="item.link" :title="item.title">
          <font-awesome-icon class="h-full w-full" :icon="['fab', item.icon]"  size="3x"  />
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
          link: 'https://github.com/cbaney',
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
