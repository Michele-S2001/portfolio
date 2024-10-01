<template>
  <div class="container">
    <!-- inizio header 
      IDEE: possibilità di creare un componente apposta per l'header
    -->
    <header class="flex justify-between items-center my-5">
      <div>
        <NuxtLink to="/" class="text-xl font-semibold hover:bg-gray-200">Michele Serafini</NuxtLink>
      </div>
      <Navbar />
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