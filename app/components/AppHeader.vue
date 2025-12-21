<template>
  <nav class="bg-white shadow-md z-[1100] fixed top-0 w-full">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-20">
        <div class="flex-shrink-0">
          <NuxtLink
            to="/"
            class="flex items-center"
          >
            <div class="h-24 w-24 md:h-32 md:w-32">
              <img
                src="/logo.svg"
                alt="UB Tours Logo"
                class="h-full w-full object-contain"
                width="139"
                height="104"
                loading="lazy"
              >
            </div>
          </NuxtLink>
        </div>

        <div class="hidden md:block">
          <div class="flex items-baseline gap-7">
            <template
              v-for="item in navItems"
              :key="item.name"
            >
              <NuxtLink
                :to="item.href"
                :class="[
                  'px-3 py-2 text-sm font-medium transition-colors duration-200 whitespace-nowrap',
                  item.current
                    ? 'text-green-700 border-b-2 border-green-600'
                    : 'text-gray-700 hover:text-green-700 md:border-b-2 border-transparent hover:border-green-300',
                ]"
                :aria-current="item.current ? 'page' : undefined"
              >
                {{ item.name }}
              </NuxtLink>
            </template>
          </div>
        </div>

        <div class="flex items-center">
          <div class="hidden md:flex">
            <BaseButton
              label="Konsultasi"
              icon-name="fluent:person-support-32-filled"
            />
          </div>

          <div class="flex md:hidden">
            <button
              type="button"
              class="inline-flex items-center justify-center p-2 rounded-md text-gray-600 hover:text-gray-800 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-green-500"
              aria-controls="mobile-menu"
              :aria-expanded="isMobileMenuOpen"
              @click="toggleMobileMenu"
            >
              <svg
                v-if="!isMobileMenuOpen"
                class="block h-6 w-6"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                aria-hidden="true"
              ><path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              /></svg>
              <svg
                v-else
                class="block h-6 w-6"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                aria-hidden="true"
              ><path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              /></svg>
            </button>
          </div>
        </div>
      </div>
    </div>

    <Transition
      enter-active-class="transition-all ease-out duration-300"
      enter-from-class="transform -translate-y-full opacity-0"
      enter-to-class="transform translate-y-0 opacity-100"
      leave-active-class="transition-all ease-in duration-200"
      leave-from-class="transform translate-y-0 opacity-100"
      leave-to-class="transform -translate-y-full opacity-0"
    >
      <div
        v-if="isMobileMenuOpen"
        id="mobile-menu"
        class="md:hidden absolute w-full bg-white shadow-xl border-t border-gray-100"
      >
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <template
            v-for="item in navItems"
            :key="item.name"
          >
            <NuxtLink
              :to="item.href"
              :class="[
                'block px-3 py-2 rounded-md text-base font-medium transition-colors duration-200',
                item.current
                  ? 'bg-green-100 text-green-700'
                  : 'text-gray-700 hover:bg-gray-50 hover:text-green-700',
              ]"
              :aria-current="item.current ? 'page' : undefined"
              @click="closeMobileMenu"
            >
              {{ item.name }}
            </NuxtLink>
          </template>

          <button class="w-full mt-2 bg-green-700 hover:bg-green-800 text-white px-4 py-2 rounded-lg text-base font-medium shadow-md transition-colors duration-200">
            <Icon
              name="mdi:headset"
              class="w-5 h-5 inline-block mr-1 -mt-0.5"
            />
            Konsultasi
          </button>
        </div>
      </div>
    </Transition>
  </nav>
</template>

<script setup lang="ts">
import { ref, computed, watch } from 'vue'
import { useRoute } from '#app'

const navData = [
  { name: 'UB Tours', href: '/ub-tours' },
  { name: 'Wisata Halal', href: '/wisata-halal' },
  { name: 'Promo & Paket', href: '/promo' },
  { name: 'Agen Resmi', href: '/agen' },
  { name: 'Berita dan Artikel', href: '/artikel' },
]

const isMobileMenuOpen = ref(false)

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}

const route = useRoute()

const navItems = computed(() => {
  return navData.map(item => ({
    ...item,
    current: item.href === route.path,
  }))
})

watch(
  () => route.path,
  () => {
    closeMobileMenu()
  },
)
</script>
