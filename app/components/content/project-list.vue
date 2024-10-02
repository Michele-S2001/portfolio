<template>
  <div class="not-prose">
    <section v-if="error">Something went wrong, try again</section>
    <section v-else-if="!(status === 'success')">Loading...</section>
    <section v-else>
      <ul class="grid grid-cols-1 gap-4">
        <li v-for="repo in repoWithLang" :key="repo.id" 
          class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 dark:hover:bg-gray-600 font-mono">
          <a :href="repo.html_url" target="_blank" class="font-semibold">
            <div class="flex justify-between items-center mb-3">
              <h3 class="">{{ repo.name }}</h3>
              <span>{{ repo.stargazers_count }} ⭐</span>
            </div>
            <p class="text-sm bg-teal-200 dark:text-gray-900 inline-block px-2 rounded-md">{{ repo.language }}</p>
          </a>
        </li>
      </ul>
    </section>
  </div>
</template>

<script setup>
// IDEE: creare un filtro in base al linguaggio principale
const { data, status, error } = await useFetch('https://api.github.com/users/michele-s2001/repos', {
  query: {sort: 'updated'}
});

const repoWithLang = computed(
  () => data.value.filter(repo => repo.language)
)
</script>