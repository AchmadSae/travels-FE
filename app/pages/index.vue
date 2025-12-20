<template>
  <div>
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="md:h-screen flex flex-col gap-7 pt-36 md:pt-20 items-center justify-center">
        <div class="text-2xl md:text-4xl font-bold text-[#F8A401]">
          UB Islamic Vacation
        </div>
        <div class="flex max-sm:flex-col items-center gap-8 md:gap-[132px] md:p-12">
          <img
            src="/logo_home.svg"
            alt="UB Tours Home Logo"
            class=" object-contain"
            width="350"
            height="250"
            loading="lazy"
          >
          <div class="flex flex-col gap-4">
            <div class="flex flex-col gap-2">
              <div class="text-white text-justify">
                Maecenas dignissim justo eget nulla rutrum molestie. Maecenas lobortis sem dui, vel rutrum risus tincidunt ullamcorper. Proin eu enim metus. Vivamus sed libero ornare, tristique quam in, gravida enim. Nullam ut molestie arcu, at hendrerit elit. Morbi laoreet elit at ligula molestie, nec molestie mi blandit. Suspendisse cursus tellus sed augue ultrices, quis tristique nulla sodales. Suspendisse eget lorem eu turpis vestibulum pretium. Suspendisse potenti. Quisque malesuada enim sapien, vitae placerat ante feugiat eget. Quisque vulputate odio neque, eget efficitur libero condimentum id. Curabitur id nibh id sem dignissim finibus ac sit amet magna.
              </div>
              <div class="text-[#F8A401]">
                Tim Smith
              </div>
              <div class="text-white">
                British Dragon Boat Racing Association
              </div>
            </div>
            <div class="flex gap-6">
              <Icon
                v-for="value in [1, 1, 1, 1, 1, 1]"
                :key="value"
                name="fluent:person-support-32-filled"
                class="w-5 h-5 text-white"
              />
            </div>
          </div>
        </div>
      </div>
      <div class="md:h-screen flex flex-col gap-10 pt-20 items-center justify-center">
        <div class="text-2xl md:text-4xl font-bold text-white max-w-96 max-sm:text-center">
          Pilih Kita !.. Benefit Anda Pasti Terpenuhi
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6 md:gap-20 md:max-w-5xl">
          <div
            v-for="value in [1, 1, 1]"
            :key="value"
            class="bg-white text-black p-6 text-center flex flex-col gap-4 items-center justify-center"
          >
            <Icon
              name="fluent:person-support-32-filled"
              class="w-12 h-12"
            />
            <div class="max-w-40 font-bold">
              Membership Organisations
            </div>
            <div>
              Our membership management software provides full automation of membership renewals and payments
            </div>
          </div>
        </div>
        <div class="bg-white rounded-2xl p-6 max-sm:gap-6 grid md:grid-cols-2 w-full items-center">
          <div>
            <div class="text-xl max-sm:text-center">
              Helping a local
            </div>
            <div class="text-xl text-[#F8A401] max-sm:text-center">
              business reinvent itself
            </div>
            <div class="max-sm:text-center">
              We reached here with our hard work and dedication
            </div>
          </div>
          <div class="grid grid-cols-2 justify-items-center gap-6">
            <div
              v-for="value in [1, 1, 1, 1]"
              :key="value"
              class="flex flex-col md:flex-row gap-4 max-sm:justify-center max-sm:items-center max-w-min"
            >
              <Icon
                name="fluent:person-support-32-filled"
                class="w-12 h-12"
              />
              <div>
                <div class="font-bold max-sm:text-center">
                  2,245,341
                </div>
                <div class="text-gray-400 max-sm:text-center">
                  Members
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="bg-[#414D55] w-full text-white">
      <div class="flex gap-14 flex-col max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 lg:py-14">
        <div class="block md:flex justify-between items-center">
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
        <ClientOnly>
          <swiper-container
            ref="containerRef"
            :loop="true"
            :slides-per-view="3"
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

definePageMeta({
  layout: 'default',
})
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
