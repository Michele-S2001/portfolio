<template>
  <div class="container">
    <header class="flex justify-between items-start md:items-center my-5">
      <div class="flex items-center gap-10">
        <div class="hidden md:block">
          <NuxtLink to="/" class="text-xl font-semibold hover:bg-gray-200 dark:hover:bg-gray-800">Michele Serafini</NuxtLink>
        </div>
        <Navbar />
      </div>
      <ClientOnly>
        <ColorModeSelector />
      </ClientOnly>
    </header>
    <!-- fine header -->
    <!-- inizio main content -->
    <main class="mt-10">
      <slot></slot>
    </main>
    <!-- fine main content -->
  </div>
</template>

<script setup>
useHead({
  titleTemplate: 'Portfolio - %s'
})
</script>

<style>
body {
  @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-300
}
</style>