<template>
  <div class="bg-[#434D54] w-full text-white">
    <div class="flex gap-7 md:gap-14 flex-col max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-24 md:py-28">
      <div class="max-sm:flex-col gap-4 flex justify-between items-center">
        <div class="flex flex-col gap-2">
          <div class="text-2xl md:text-4xl">
            Our Customer Feedback
          </div>
          <div class="text-lg md:text-2xl">
            Don’t take our word for it. Trust our customers
          </div>
        </div>
        <div>
          <div class="flex gap-3 max-sm:justify-between">
            <button class="prev-el border border-slate-700 hover:bg-slate-800 px-5 py-2 rounded-lg flex items-center gap-2 transition-all disabled:opacity-30">
              <Icon
                name="heroicons:chevron-left"
                class="w-5 h-5"
              />
              <span>Previous</span>
            </button>
            <button class="next-el bg-slate-800 border border-slate-700 hover:bg-slate-700 px-5 py-2 rounded-lg flex items-center gap-2 transition-all">
              <span>Next</span>
              <Icon
                name="heroicons:chevron-right"
                class="w-5 h-5"
              />
            </button>
          </div>
        </div>
        <!-- Navigator in here -->
      </div>
      <div class="w-full">
        <ClientOnly>
          <swiper-container
            ref="containerRef"
            :loop="true"
            :slides-per-view="1"
            :space-between="20"
            :navigation="{
              prevEl: '.prev-el',
              nextEl: '.next-el',
            }"
            :pagination="{
              clickable: true,
              enabled: true,
              type: 'bullets',
            }"
            :breakpoints="{
              768: { slidesPerView: 2 },
              1024: { slidesPerView: 3 },
              1280: { slidesPerView: 4 },
            }"
            class=" gap-4 max-w-5xl justify-center items-center mx-auto"
          >
            <swiper-slide
              v-for="(slide, idx) in slides"
              :key="idx"
              style=""
            >
              <div
                class="bg-white rounded-2xl shadow-lg p-6 max-w-sm w-full"
              >
                <div class="flex items-center gap-4 mb-4">
                  <NuxtImg
                    src="https://i.redd.it/e3zaq33rfn791.jpg"
                    class="w-16 h-16 rounded-lg object-cover"
                  />

                  <div class="flex gap-1 text-amber-400">
                    <svg
                      v-for="val in [1, 1, 1, 1, 1]"
                      :key="val"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 24 24"
                      fill="currentColor"
                      class="w-6 h-6"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.007Z"
                        clip-rule="evenodd"
                      />
                    </svg>
                  </div>
                </div>

                <h3 class="text-2xl font-bold text-slate-900 mb-3">
                  Floyd Miles
                </h3>

                <p class="text-slate-600 text-base leading-relaxed line-clamp-3">
                  Amet minim mollit non deserunt ullamco est sit aliqua dolor do amet
                  sint. Velit officia consequat duis enim v...
                </p>
              </div>
            </swiper-slide>
          </swiper-container>
        </ClientOnly>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useSwiper } from '#imports'
import { ref } from 'vue'

const containerRef = ref < any > (null)
const slides = ref(Array.from({ length: 10 }))
const swiper = useSwiper(containerRef, {
  effect: 'creative',
  loop: true,
  autoplay: {
    delay: 1000,
  },
  creativeEffect: {
    prev: {
      shadow: true,
      translate: [0, 0, -400],
    },
    next: {
      shadow: true,
      translate: [0, 0, -400],
    },
  },
})

onMounted(() => {
  console.log('swiper')
})
</script>

<style scoped>
swiper-container {
  /* --swiper-pagination-bullet-inactive-color: #ffffff;
  --swiper-pagination-bullet-inactive-opacity: 0.3;
  --swiper-pagination-color: #fbbf24; */
  /* --swiper-pagination-bottom: -30px; */
  /* padding-bottom: 60px; */
  /* --swiper-pagination-bullet-size: 12px;
  --swiper-pagination-bullet-width: 12px;
  --swiper-pagination-bullet-horizontal-gap: 6px; */
}
swiper-slide {
  height: auto;
}
</style>
