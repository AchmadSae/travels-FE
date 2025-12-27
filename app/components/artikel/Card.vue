<script setup lang="ts">
interface Props {
  category?: string;
  title?: string;
  description?: string;
  imageSrc?: string;
  imageAlt?: string;
}

// Nilai default jika props tidak diisi (sesuai gambar)
withDefaults(defineProps<Props>(), {
  category: 'BUSINESS',
  title: 'Hikmah dari ciptaan Tuhan di Alam..',
  description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Non blandit massa enim nec.',
  imageSrc: 'https://m.media-amazon.com/images/M/MV5BMjBlNTExMDAtMWZjZi00MDc5LWFkMjgtZDU0ZWQ5ODk3YWY5XkEyXkFqcGc@._V1_FMjpg_UX1000_.jpg',
  imageAlt: 'Islamic calligraphy and mosque architecture',
});
</script>

<template>
  <section class="w-full hover:cursor-pointer">
    <div class="max-w-5xl mx-auto">
      <div class="flex flex-col md:flex-row items-center md:gap-12 lg:gap-16">
        <div class="w-full md:w-3/12 mb-8 md:mb-0 shrink-0">
          <div class="relative overflow-hidden rounded-sm shadow-sm aspect-[3/5] bg-white">
            <NuxtImg
              :src="imageSrc"
              :alt="imageAlt"
              loading="lazy"
              class="w-full h-full object-cover hover:scale-105 transition-transform duration-500 ease-in-out"
              format="webp"
            />
          </div>
        </div>

        <div class="w-full md:w-9/12 text-left">
          <span class="block text-purple-600 font-bold tracking-[0.2em] text-sm uppercase mb-4">
            {{ category }}
          </span>

          <h2 class="text-2xl md:text-4xl font-extrabold text-gray-900 mb-6 leading-tight">
            {{ title }}
          </h2>

          <p class="text-gray-500 text-lg leading-relaxed line-clamp-4">
            {{ description }}
          </p>
        </div>

      </div>
    </div>
  </section>
</template>