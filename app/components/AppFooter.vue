<script setup lang="ts">
const footerMenu = ref([
  {
    title: 'Privacy Policy',
    link: '#',
  },
  {
    title: 'Terms of Use',
    link: '#',
  },
  {
    title: 'Legal',
    link: '#',
  },
  {
    title: 'Site Map',
    link: '#',
  },
])

const activeIndex = ref<number | null>(0)

const toggle = (index: number) => {
  activeIndex.value = activeIndex.value === index ? null : index
}
</script>
<template>
  <div class="bg-[#434D54] w-full text-white rounded-t-3xl">
    <div class="flex flex-col gap-8 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-14 md:py-28">
      <div class="grid md:grid-cols-3 gap-7 justify-between">
        <div>
          <div>
            <!-- logo here -->
            <span class="text-2xl">Macat Megatrons</span>
          </div>
          <div class="text-sm text-[#EBEBEB]">
            Macat Megatrons is a thriving community where innovators, professionals, and enthusiasts come together to share knowledge, collaborate, and grow.
          </div>
        <!-- logo -->
        </div>
        <div class="grid grid-cols-2 md:flex md:flex-row gap-10 md:justify-center">
          <div class="flex flex-col gap-2">
            <div class="text-xl">
              Company
            </div>
            <div class="flex flex-col gap-2">
              <div
                v-for="value in [1, 1, 1, 1]"
                :key="value"
                class="text-sm text-[#EBEBEB]"
              >
                About Us
              </div>
            </div>
          </div>
          <div class="flex flex-col gap-2">
            <div class="text-xl">
              Developers
            </div>
            <div class="flex flex-col gap-2">
              <div
                v-for="value in [1, 1, 1, 1]"
                :key="value"
                class="text-sm text-[#EBEBEB]"
              >
                Web Technologies
              </div>
            </div>
          </div>
        </div>
        <div class="grid grid-cols-2 md:flex md:flex-row gap-10 md:justify-center">
          <div class="flex flex-col gap-2">
            <div class="text-xl">
              Our Communities
            </div>
            <div class="flex flex-col gap-2">
              <div
                v-for="value in [1, 1, 1]"
                :key="value"
                class="text-sm text-[#EBEBEB]"
              >
                MM Communities
              </div>
            </div>
          </div>
          <div class="flex flex-col gap-2">
            <div class="text-xl">
              Contact
            </div>
            <div class="flex flex-col gap-2">
              <div
                v-for="value in [1, 1]"
                :key="value"
                class="text-sm text-[#EBEBEB]"
              >
                Web Technologies
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="flex max-sm:flex-col gap-2 justify-between text-[#EBEBEB] text-xs items-center">
        <span class="">
          © 2025 Macat Megatrons. All rights reserved.
        </span>
        <div class="flex gap-8">
          <span class="" v-for="value in footerMenu" :key="value.title">
            {{ value.title }}
          </span>
        </div>
      </div>
    </div>
  </div>
</template>
