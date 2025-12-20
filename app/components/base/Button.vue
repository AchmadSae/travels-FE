<template>
  <button
    v-bind="$attrs"
    class="flex items-center gap-2 bg-green-700 hover:bg-green-800 text-white px-4 py-2 rounded-lg text-sm font-medium shadow-md transition-colors duration-200"
  >
    <Icon
      :name="iconName"
      class="w-5 h-5"
      v-if="iconName"
    />
    <span>{{ label }}</span>
  </button>
</template>

<script setup lang="ts">
interface Props {
  label?: string
  iconName?: string
}

withDefaults(defineProps<Props>(), {
  label: 'Konsultasi',
})
</script>