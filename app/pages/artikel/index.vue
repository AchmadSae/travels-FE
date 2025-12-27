<template>
  <div class="bg-gradient-to-br from-white to-gray-400">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="md:max-w-2xl mx-auto min-h-screen flex flex-col gap-7 pt-36 md:pt-20 items-center justify-center">
        <div class="flex gap-6 md:gap-24 items-center">
          <Icon
            name="fluent-color:news-16"
            class="h-24 w-24 md:h-96 md:w-96"
          />
          <div class="text-2xl md:text-5xl font-bold">
            Biyar makin paham. lihat yuk artikel di bawah ini..
          </div>
        </div>
      </div>
      <div class="flex flex-col gap-8">
        <div class="flex flex-col gap-8 md:hidden">
          <LazyArtikelCategory hydrate-on-visible />
          <LazyArtikelTag hydrate-on-visible />
        </div>
        <div class="md:grid grid-cols-12 mb-8 gap-12">
          <div class="col-span-8 flex flex-col md:gap-8 gap-12">
            <LazyArtikelCard
              v-for="value in [1, 1, 1, 1]"
              :key="value"
              hydrate-on-visible
            />
          </div>
          <div class="col-span-1 max-sm:hidden" />
          <div class="col-span-3 flex flex-col gap-8 max-sm:hidden">
            <LazyArtikelCategory hydrate-on-visible />
            <LazyArtikelTag hydrate-on-visible />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped>

</style>
