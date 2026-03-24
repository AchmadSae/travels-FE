<script setup lang="ts">
const route = useRoute()

// Ensure route.meta properties are properly typed
const routeClass = computed<string | string[] | Record<string, boolean>>(() => route.meta.class as string | string[] | Record<string, boolean> || '')
const routeStyle = computed<Record<string, any>>(() => route.meta.style as Record<string, any> || {})
</script>

<template>
  <div
    class="bg-gray-400"
    :style="routeStyle"
    :class="routeClass"
  >
    <AppHeader />
    <main>
      <slot />
    </main>
  
  </div>
</template>

<style></style>
