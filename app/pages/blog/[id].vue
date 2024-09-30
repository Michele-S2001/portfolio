<template>
  <h1>
    article detail
  </h1>
  <div>Post id is {{ route.params.id }}</div>
</template>

<script setup>
const route = useRoute();

console.log(route);

</script>