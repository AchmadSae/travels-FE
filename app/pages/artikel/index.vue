<template>
  <div class="bg-gradient-to-br from-white to-gray-400">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="md:min-h-screen" />
      <div class="md:grid grid-cols-12 mb-8 gap-12">
        <div class="col-span-8 flex flex-col md:gap-8 gap-12">
          <ArtikelCard
            v-for="value in [1, 1, 1, 1]"
            :key="value"
          />
        </div>
        <div class="col-span-1 max-sm:hidden" />
        <div class="col-span-3 flex flex-col gap-6">
          <ArtikelCategory />
          <ArtikelTag />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped>

</style>
