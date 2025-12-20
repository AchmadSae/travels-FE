<template>
  <div class="bg-white rounded-lg shadow-xl overflow-hidden p-6 md:p-8 flex flex-col md:flex-row gap-8 border border-gray-100">
    
    <div class="flex-1 space-y-2 text-xs">
      <span class="text-sky-500 font-bold tracking-wider text-sm uppercase">
        {{ category }}
      </span>
      
      <h2 class="font-extrabold text-sm text-slate-800 leading-tight">
        {{ title }}
      </h2>

      <div class="flex items-center gap-4">
        <div class="bg-sky-50 p-2 px-4 rounded-lg flex items-center gap-2 border border-sky-100">
          <span class="font-bold text-slate-700">$</span>
        </div>
        <span class="font-bold text-slate-700">{{ price }}</span>
      </div>

      <p class="text-slate-500 leading-relaxed">
        {{ description }}
      </p>

      <div class="space-y-1 pt-1">
        <div v-for="(item, index) in details" :key="index" class="flex items-center">
          <span class="w-20 text-slate-500">{{ item.label }}:</span>
          <span class="font-semibold text-slate-700">{{ item.value }}</span>
        </div>
      </div>
    </div>

    <div class="flex-1 relative group cursor-pointer">
      <NuxtImg
        :src="imageSrc"
        :alt="title"
        loading="lazy"
        class="w-full h-full object-cover rounded-lg shadow-lg transition-transform duration-500 group-hover:scale-105"
        width="500"
        height="500"
        format="webp"
      />
      <div class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent rounded-3xl pointer-events-none"></div>
    </div>
  </div>
</template>

<script setup lang="ts">
// Interface untuk mendukung Type Safety di Nuxt 4
interface DetailItem {
  label: string
  value: string | number
}

interface Props {
  category?: string
  title?: string
  price?: string | number
  description?: string
  imageSrc: string
  details: DetailItem[]
}

const props = withDefaults(defineProps<Props>(), {
  category: 'CITY BACKPACKS',
  title: 'Ramadhan Karim Promo Discount',
  price: '254.99',
  description: 'The lightweight tee is made of soft jersey for a casual look and feel.',
  details: () => []
})
</script>