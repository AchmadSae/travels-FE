<template>
  <div>
    <h2 class="text-2xl md:text-4xl font-extrabold text-gray-900 mb-6 leading-tight">
      Categories
    </h2>
    <div class="grid grid-cols-2 md:grid-cols-1 gap-4 md:gap-4">
      <div
        v-for="value in [1, 2, 3, 4]"
        :key="value"
        class="flex gap-6 items-center p-4 rounded-lg border border-yellow-500 cursor-pointer hover:bg-yellow-500"
        :class="value == 1 ? 'bg-yellow-500' : ''"
      >
        <div class="bg-white rounded-lg p-3 flex items-center">
          <Icon
            name="fluent:person-support-32-filled"
            class="w-6 h-6"
          />
        </div>
        <span class="text-base font-semibold md:text-xl">Tauhid</span>
      </div>
    </div>
  </div>
</template>
