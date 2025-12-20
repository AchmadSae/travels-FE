<template>
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
</template>
