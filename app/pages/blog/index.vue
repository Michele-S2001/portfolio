<template>
  <section>
    <h1 class="text-2xl font-bold mb-7">All blog posts list</h1>
    <ul>
      <li v-for="post in posts" :key="post._path">
        <NuxtLink :to="post._path">{{ post.title }}</NuxtLink>
      </li>
    </ul>
  </section>
</template>

<script setup>
useSeoMeta({
  title: 'blog'
})

const { data:posts } = await useAsyncData(
  'blog-list', () => queryContent('/blog').only(['_path', 'title']).find()
);
</script>