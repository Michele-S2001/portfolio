<template>
  <article class="prose dark:prose-invert prose-pre:bg-white dark:prose-pre:bg-gray-800 prose-pre:text-gray-700 prose-img:max-w-28 dark:prose-pre:text-gray-300 max-w-none">
    <ContentDoc v-slot="{ doc }">
      {{ doc.body.toc.links }}
      <div class="grid grid-cols-6 gap-16">
        <div :class="[ doc.toc ? 'col-span-4' : 'col-span-full']">
          <ContentRenderer :value="doc" />
        </div>
        <div class="col-span-2" v-if="doc.toc">
          <aside class="sticky top-8">
            <h4>Table of contents</h4>
            <nav class="not-prose">
              <TocLinks :links="doc.body.toc.links"/> 
            </nav>
          </aside>
        </div>
      </div>
    </ContentDoc>
  </article>
</template>

<script setup>
const route = useRoute();
console.log(route.params.slug);
</script>