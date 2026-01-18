<script setup lang="ts">
interface PromoProps {
  title: string;
  discountPercentage: string;
  originalPrice: string;
  discountedPrice: string;
  features: string[];
  image: string;
}

const props = defineProps<PromoProps>();
</script>

<template>
  <div 
  @click="$router.push(`/promo/${title}`)"
  class="bg-white hover:cursor-pointer w-full rounded-[1.5rem] shadow-lg border border-gray-100 p-5 flex items-stretch gap-4 h-full hover:shadow-xl transition-shadow duration-300 relative overflow-hidden group">
    
    <div class="flex-1 flex flex-col justify-between min-w-0">
      
      <div>
        <h1 class="text-5xl md:text-6xl font-bold text-[#6FCF97] tracking-tighter discount-text mb-1">
          {{ discountPercentage }}
        </h1>

        <h2 class="text-sm md:text-base font-bold text-gray-700 leading-tight mb-2 line-clamp-2">
          {{ title }}
        </h2>

        <div class="mb-3">
          <p class="text-[10px] md:text-xs text-[#D35D47] line-through decoration-[#D35D47]">
            {{ originalPrice }}
          </p>
          <p class="text-sm md:text-base font-bold text-[#2E7D58]">
            {{ discountedPrice }}
          </p>
        </div>
      </div>

      <div>
        <p class="text-[10px] md:text-xs text-gray-400 font-medium mb-1">Free:</p>
        <ul class="space-y-0.5 md:text-xs">
          <li 
            v-for="(item, index) in features" 
            :key="index"
            class="flex items-center gap-1.5 text-[10px] text-gray-500 font-medium"
          >
            <span class="w-1 h-1 bg-gray-400 rounded-full flex-shrink-0"></span>
            <span class="truncate">{{ item }}</span>
          </li>
        </ul>
      </div>
    </div>

    <div class="w-28 sm:w-32 shrink-0 relative">
      <div class="w-full h-full rounded-2xl overflow-hidden bg-gray-100">
        <NuxtImg
          :src="image"
          :alt="title"
          class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
          loading="lazy"
        />
      </div>
    </div>

  </div>
</template>

<style scoped>
.discount-text {
  color: #6FCF97; 
  /* Stroke disesuaikan tipisnya untuk ukuran font lebih kecil */
  -webkit-text-stroke: 1.5px #EFA63E; 
  text-shadow: 1px 1px 0px rgba(239, 166, 62, 0.2);
}
</style>