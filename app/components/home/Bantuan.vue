<script setup lang="ts">
const faqItems = ref([
  {
    title: 'Cara Pembayaran ?',
    content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cursus nisl purus tempor sapien est. Integer sed viverra pellentesque orci erat viverra hendrerit duis cursus.'
  },
  {
    title: 'Section Title',
    content: 'Penjelasan detail untuk section ini bisa diletakkan di sini.'
  },
  {
    title: 'Section Title',
    content: 'Penjelasan detail untuk section ini bisa diletakkan di sini.'
  }
])

const activeIndex = ref<number | null>(0)

const toggle = (index: number) => {
  activeIndex.value = activeIndex.value === index ? null : index
}
</script>

<template>
  <div class="bg-[#E2E2E2]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-24 md:py-28">
        <h2 class="text-3xl font-bold text-center text-slate-700 mb-8">Perlu Bantuan ?</h2>

    <div class="bg-white rounded-lg shadow-sm border border-gray-200 overflow-hidden">
      <div v-for="(item, index) in faqItems" :key="index" class="border-b last:border-b-0 border-gray-200">
        <button
          @click="toggle(index)"
          class="w-full flex justify-between items-center p-5 text-left transition-colors hover:bg-gray-50"
        >
          <span class="font-semibold text-slate-800">{{ item.title }}</span>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5 transform transition-transform duration-300"
            :class="{ 'rotate-180': activeIndex === index }"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
          </svg>
        </button>

        <div
          class="grid transition-all duration-300 ease-in-out"
          :class="[
            activeIndex === index 
              ? 'grid-rows-[1fr] opacity-100' 
              : 'grid-rows-[0fr] opacity-0'
          ]"
        >
          <div class="overflow-hidden">
            <div class="p-5 pt-0 text-slate-600 leading-relaxed text-sm">
              {{ item.content }}
            </div>
          </div>
        </div>
      </div>
    </div>
    </div>
  </div>
</template>