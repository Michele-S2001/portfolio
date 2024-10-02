<template>
  <section class="not-prose font-mono">
    <header class="column text-gray-500 text-sm select-none">
      <span>date</span>
      <span>title</span>
    </header>
    <ul>
      <li v-for="post in posts" :key="post._path">
        <NuxtLink :to="post._path" class="column hover:bg-gray-100 dark:hover:bg-gray-700">
          <div class="text-gray-600 dark:text-gray-500">2023</div>
          <p>{{ post.title }}</p>
        </NuxtLink>
      </li>
    </ul>
  </section>
</template>

<script setup>
useSeoMeta({
  title: 'blog'
})

const { data:posts } = await useAsyncData(
  'blog-list', 
  () => queryContent('/blog')
    .only(['_path', 'title'])
    .where({ '_path': {$ne: '/blog'}})
    .find()
);
</script>

<style scoped>
.column {
  @apply flex items-center space-x-8 py-2 border-b border-gray-300 dark:border-b-gray-500
}

</style>