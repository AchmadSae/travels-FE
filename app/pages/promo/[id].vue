<template>
  <div class="bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-8 mt-32 md:mt-40">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div
          id="left-sect"
          class="flex flex-col gap-6"
        >
          <div class="text-2xl md:text-4xl font-bold text-[#014F5A]">
            Overview Paket
          </div>
          <div class="text-[#667085] flex flex-col gap-4">
            <span>
              A modern UI Kit for building custom mapping experiences inspired by Google Maps. Includes pre-made components, styles, and screen variations for seamless design customization.
            </span>
            <span>
              A modern UI Kit for building custom mapping experiences inspired by Google Maps. Includes pre-made components, styles, and screen variations for seamless design customization.
            </span>
          </div>
          <div class="flex justify-center">
            <BaseButton
              label="Daftar Sekarang"
              icon-name="fluent:airplane-take-off-24-regular"
            />
          </div>
        </div>
        <div id="right-sect">
          <div class="flex flex-col gap-4">
            <NuxtImg
              src="/detail_1.png"
              alt="/detail_1.png"
              loading="lazy"
              class="w-full h-full object-cover rounded-lg shadow-lg transition-transform duration-500 group-hover:scale-105"
              width="500"
              height="500"
              format="webp"
            />
            <div class="flex flex-col md:flex-row gap-4">
              <NuxtImg
                src="/detail_2.png"
                alt="/detail_2.png"
                loading="lazy"
                class="w-full h-full object-cover rounded-lg shadow-lg transition-transform duration-500 group-hover:scale-105"
                width="500"
                height="500"
                format="webp"
              />
              <NuxtImg
                src="/detail_3.png"
                alt="/detail_3.png"
                loading="lazy"
                class="w-full h-full object-cover rounded-lg shadow-lg transition-transform duration-500 group-hover:scale-105"
                width="500"
                height="500"
                format="webp"
              />
            </div>
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
