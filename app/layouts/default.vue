<script setup lang="ts">
const route = useRoute()
</script>

<template>
  <div
    class="bg-gray-400"
    :style="route.meta.style"
  >
    <AppHeader />
    <main>
      <slot />
    </main>
    <LazyAppFooter hydrate-on-visible />
  </div>
</template>
