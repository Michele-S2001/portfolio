<template>
  <nav class="hidden md:block font-mono">
    <ul class="flex flex-col md:flex-row gap-2 md:gap-4">
      <li>
        <NuxtLink to ="/" class="link">Main</NuxtLink>
      </li>
      <li>
        <NuxtLink to ="/about" class="link">About</NuxtLink>
      </li>
      <li>
        <NuxtLink to ="/blog" class="link">Blog</NuxtLink>
      </li>
      <li>
        <NuxtLink to ="/projects" class="link">Projects</NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.link {
  @apply p-1 hover:bg-gray-200 dark:hover:bg-gray-800 text-2xl md:text-base
}
</style>