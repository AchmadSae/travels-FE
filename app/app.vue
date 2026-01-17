<template>
  <NuxtLayout :name="layout">
    <NuxtRouteAnnouncer />
    <NuxtPage />
  </NuxtLayout>
</template>

<script setup lang="ts">
const layout = 'default'
</script>
