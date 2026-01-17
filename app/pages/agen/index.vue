<template>
  <div class="">
    <AgenBanner />
    <div>
      <AgenMap />
    </div>
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 my-32 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 justify-items-center">
      <AgenCard
        v-for="(item, index) in agents"
        :key="index"
        :agent="item"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
const agents = [
  {
    name: 'Barokah UB Agent',
    image: 'https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?q=80&w=2070&auto=format&fit=crop',
    location: 'Jakarta Selatan',
    phone: '242-556-5586',
    hours: 'Senin - Jumat 8:00 AM - 5:00 PM',
    additionalInfo: {
      label: 'Parking Availability',
      value: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor.',
    },
  },
  {
    name: 'Cabang Bandung',
    image: 'https://images.unsplash.com/photo-1554469384-e58fac16e23a?q=80&w=1000&auto=format&fit=crop',
    location: 'Bandung Wetan',
    phone: '022-123-4567',
    hours: 'Setiap Hari 9:00 AM - 9:00 PM',
    additionalInfo: {
      label: 'Fasilitas',
      value: 'Musholla tersedia, Parkir luas, Free WiFi.',
    },
  },
  {
    name: 'Cabang Tangerang',
    image: 'https://images.unsplash.com/photo-1554469384-e58fac16e23a?q=80&w=1000&auto=format&fit=crop',
    location: 'Bandung Wetan',
    phone: '022-123-4567',
    hours: 'Setiap Hari 9:00 AM - 9:00 PM',
    additionalInfo: {
      label: 'Fasilitas',
      value: 'Musholla tersedia, Parkir luas, Free WiFi.',
    },
  },
]
</script>

<style scoped>

</style>
