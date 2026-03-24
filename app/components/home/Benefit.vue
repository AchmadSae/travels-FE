<template>
  <div class="md:h-screen flex flex-col gap-10 pt-10  items-center justify-center">
    <div class="text-2xl md:text-4xl font-bold text-white max-w-100 max-sm:text-center">
      Manfaat Bergabung dengan UB Islamic Vacation
    </div>
    <div
    ref="fadeEl" 
    :class="['grid grid-cols-1 md:grid-cols-3 gap-6 md:gap-20 md:max-w-5xl transition-all duration-700 ease-out', isVisible ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-6']">
      <div
        class=
          'bg-white text-black p-6 text-center flex flex-col gap-4 items-center justify-center rounded-2xl'>
        <Icon
          name="clarity:license-solid"
          class="w-12 h-12"
        />
        <div class="max-w-40 font-bold">
          License to Travel
        </div>
        <div>
          Trusted by thousands of travelers, UB Islamic Vacation is your go-to platform for all your travel needs. Join our community and experience the benefits of being a member today!
        </div>
      </div>
      <div
        class="bg-white text-black p-6 text-center flex flex-col gap-4 items-center justify-center rounded-2xl"
      >
        <Icon
          name="streamline-ultimate:fiber-access-1-bold"
          class="w-12 h-12"
        />
        <div class="max-w-40 font-bold">
          Access Anywhere
        </div>
        <div>
          By joining UB Islamic Vacation, you can access exclusive travel deals, discounts, and personalized travel planning services that cater to your preferences and needs.
        </div>
      </div>
      <div
        class="bg-white text-black p-6 text-center flex flex-col gap-4 items-center justify-center rounded-2xl"
      >
        <Icon
          name="streamline-cyber:cash-bag-give"
          class="w-12 h-12"
        />
        <div class="max-w-40 font-bold">
          Refund Guarantee
        </div>
        <div>
          Our membership management software provides full automation of membership renewals and payments
        </div>
      </div>
    </div>
    <div class="bg-white text-black rounded-2xl p-6 max-sm:gap-6 grid md:grid-cols-2 w-full items-center">
      <div>
        <div class="text-xl text-green-700 font-bold max-sm:text-center">
          Helping a local
        </div>
        <div class="text-x max-sm:text-center">
          business reinvent itself
        </div>
        <div class="max-sm:text-center">
          We reached here with our hard work and dedication
        </div>
      </div>
      <div class="grid grid-cols-2 justify-items-center gap-6">
        <div
          class="flex flex-col md:flex-row gap-4 max-sm:justify-center max-sm:items-center max-w-min p-4"
        >
          <Icon
            name="material-symbols:airplane-ticket-rounded"
            class="w-20 h-20 bg-[#35312a] text-white p-4 rounded-full"
          />
          <div>
            <div class="font-bold max-sm:text-center">
              > 1000
            </div>
            <div class="text-gray-400 max-sm:text-center">
              Tickets Booked per Year
            </div>
          </div>
        </div>
        <div
          class="flex flex-col md:flex-row gap-4 max-sm:justify-center max-sm:items-center max-w-min p-4"
        >
          <Icon
            name="lsicon:badge-promotion-filled"
            class="w-20 h-20 bg-[#35312a] text-white p-4 rounded-full"
          />
          <div>
            <div class="font-bold max-sm:text-center">
              > 2% Discount
            </div>
            <div class="text-gray-400 max-sm:text-center">
              On Every Booking
            </div>
          </div>
        </div>
        <div
          class="flex flex-col md:flex-row gap-4 max-sm:justify-center max-sm:items-center max-w-min p-4"
        >
          <Icon
            name="mdi:face-agent"
            class="w-20 h-20 bg-[#35312a] text-white p-4 rounded-full"
          />
          <div>
            <div class="font-bold max-sm:text-center">
              > 10
            </div>
            <div class="text-gray-400 max-sm:text-center">
              Agent in each local 
            </div>
          </div>
        </div>
        <div
          class="flex flex-col md:flex-row gap-4 max-sm:justify-center max-sm:items-center max-w-min p-4"
        >
          <Icon
            name="material-symbols:hotel-rounded"
            class="w-20 h-20 bg-[#35312a] text-white p-4 rounded-full"
          />
          <div>
            <div class="font-bold max-sm:text-center">
              > 10
            </div>
            <div class="text-gray-400 max-sm:text-center">
              Hotels Partnered
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue'

const fadeEl = ref(null)
const isVisible = ref(false)

onMounted(() => {
  const observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        isVisible.value = true
      }
    },
    {
      threshold: 0.2, // trigger when 20% visible
    }
  )

  if (fadeEl.value) {
    observer.observe(fadeEl.value)
  }
})
</script>