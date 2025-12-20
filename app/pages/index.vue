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
      <div class="flex justify-between max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 lg:py-14">
        <div class="flex flex-col gap-2">
          <div class="text-2xl md:text-4xl">
            Our Customer Feedback
          </div>
          <div class="text-lg md:text-2xl">
            Don’t take our word for it. Trust our customers
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default',
})
</script>
