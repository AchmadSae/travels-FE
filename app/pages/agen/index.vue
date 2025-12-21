<template>
  <div class="">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-8">
      <div class="flex flex-col gap-7 pt-36 md:pb-36 md:mt-20 items-center justify-center md:min-h-screen">
        <div class="flex max-sm:flex-col gap-10 md:gap-36 items-center">
          <img
            src="/agen.svg"
            alt="Agen Logo"
            class="max-h-64 md:max-h-96 h-full object-contain"
            loading="lazy"
          >
          <div class="flex justify-center md:justify-between gap-2 md:gap-8 items-end">
            <div class="text-2xl md:text-4xl font-bold text-white md:max-w-md">
              Temukan Agent Terpercaya kami di wilayah Anda....
            </div>
            <img
              src="/google-point.svg"
              alt="Google Point Logo"
              class="max-h-14 md:max-h-24 h-full object-contain"
              loading="lazy"
            >
          </div>
        </div>
      </div>
    </div>
    <div>
      <AgenMap />
    </div>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped>

</style>
