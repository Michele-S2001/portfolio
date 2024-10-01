<template>
  <div>list</div>
  <section v-if="error">Something went wrong, try again</section>
  <section v-else-if="!(status === 'success')">Loading...</section>
  <section v-else>
    Here we display the repos!
  </section>
</template>

<script setup>
const { data, status, error } = await useFetch('https://api.github.com/users/michele-s2001/repos');
console.log(data.value);

</script>