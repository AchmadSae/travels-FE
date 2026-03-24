<template>
  <div class="flex flex-col gap-7 pt-10 md:p-10 xl:p-5 items-center justify-center">
    
    <div class="flex max-sm:flex-col items-center gap-8 md:gap-[132px] md:p-12">
      <img
        src="/logo_home.svg"
        alt="UB Tours Home Logo"
        class=" object-contain"
        width="350"
        height="250"
        loading="lazy"
      >
      <div class="flex flex-col">
        <div class="flex flex-col gap-2">
          <div class="text-2xl md:text-4xl font-bold text-[#F8A401]">
            UB Islamic Vacation
          </div>
          <div class="text-white text-justify">
            Maecenas dignissim justo eget nulla rutrum molestie. Maecenas lobortis sem dui, vel rutrum risus tincidunt ullamcorper. Proin eu enim metus. Vivamus sed libero ornare, tristique quam in, gravida enim. Nullam ut molestie arcu, at hendrerit elit. Morbi laoreet elit at ligula molestie, nec molestie mi blandit. Suspendisse cursus tellus sed augue ultrices, quis tristique nulla sodales. Suspendisse eget lorem eu turpis vestibulum pretium. Suspendisse potenti. Quisque malesuada enim sapien, vitae placerat ante feugiat eget. Quisque vulputate odio neque, eget efficitur libero condimentum id. Curabitur id nibh id sem dignissim finibus ac sit amet magna.
          </div>
          <div class="text-white">
            <BaseButton
            label="Selengkapnya"
            >
            </BaseButton>
          </div>
          <hr  class="border-gray-400">
          <di class="text-gray-400 mt-10 md:text-2xl">
            Partnership
          </di>
        </div>
        <div class="flex gap-20">
          <img width="100" height="100" class="object-contain transition delay-75 ease-out hover:scale-110 cursor-pointer" src="/partnership/ic_nuonline_dp.svg" alt="nu online" srcset="">
          <img width="100" height="100" class="object-contain transition delay-75 ease-out hover:scale-110 cursor-pointer" src="/partnership/muamalat.svg" alt="bank muamalat" srcset="">
          <img width="100" height="100" class="object-contain transition delay-75 ease-out hover:scale-110 cursor-pointer"src="/partnership/mui-retina.png" alt="mui indonensia" srcset="">
        </div>
      </div>
    </div>
  </div>
</template>
