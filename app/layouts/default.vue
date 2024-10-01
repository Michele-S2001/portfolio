<template>
  <div class="container">
    <!-- inizio header 
      IDEE: possibilità di creare un componente apposta per l'header
    -->
    <header class="flex justify-between items-center my-5">
      <div class="flex items-center space-x-10">
        <div>
          <NuxtLink to="/" class="text-xl font-semibold hover:bg-gray-200">Michele Serafini</NuxtLink>
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