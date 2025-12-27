<template>
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
          class="flex flex-col md:flex-row gap-4 max-sm:justify-center max-sm:items-center max-w-min p-4"
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
</template>
