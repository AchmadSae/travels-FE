<script setup lang="ts">
// Definisi data sosial media
const socialMedia = [
  {
    name: 'Facebook',
    url: '#',
    icon: 'fa6-brands:facebook-f', // Icon F
    shape: 'circle', // Bentuk bulat
  },
  {
    name: 'Instagram',
    url: '#',
    icon: 'fa6-brands:instagram', // Icon Kamera
    shape: 'rounded', // Bentuk kotak tumpul
  },
  {
    name: 'Google Plus',
    url: '#',
    icon: 'fa6-brands:google-plus-g', // Icon G+
    shape: 'circle', // Bentuk bulat
  },
  {
    name: 'X (Twitter)',
    url: '#',
    icon: 'fa6-brands:x-twitter', // Icon X
    shape: 'rounded', // Bentuk kotak tumpul
  },
  {
    name: 'LinkedIn',
    url: '#',
    icon: 'fa6-brands:linkedin-in', // Icon in
    shape: 'rounded', // Bentuk kotak tumpul
  },
]
</script>

<template>
  <div class="w-full flex items-center">
    <div class="flex gap-4 sm:gap-6">
      <a
        v-for="(social, index) in socialMedia"
        :key="index"
        :href="social.url"
        target="_blank"
        rel="noopener noreferrer"
        class="flex items-center justify-center transition-transform duration-300 hover:scale-110 hover:brightness-110 group"
        :class="[
          // Logika bentuk: Jika 'circle' maka rounded-full, jika tidak rounded-xl
          social.shape === 'circle' ? 'rounded-full' : 'rounded-xl',
          // Warna background icon (Abu-abu terang)
        ]"
        :aria-label="social.name"
      >
        <Icon
          :name="social.icon"
          class="text-white w-6 h-6 sm:w-5 sm:h-5"
        />
      </a>
    </div>
  </div>
</template>
