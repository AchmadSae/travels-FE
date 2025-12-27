<template>
  <h2 class="text-2xl md:text-4xl font-extrabold text-gray-900 mb-6 leading-tight">
    Categories
  </h2>
  <div class="flex flex-col gap-8">
    <div
      v-for="value in [1, 2, 3, 4]"
      :key="value"
      class="flex gap-6 items-center p-4 rounded-lg border border-yellow-500 cursor-pointer hover:bg-yellow-500"
      :class="value == 1 ? 'bg-yellow-500' : ''"
    >
      <div class="bg-white rounded-lg p-4 flex items-center">
        <Icon
          name="fluent:person-support-32-filled"
          class="w-7 h-7"
        />
      </div>
      <span class="text-lg font-semibold md:text-2xl">Tauhid</span>
    </div>
  </div>
</template>
