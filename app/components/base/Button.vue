<template>
  <button
    v-bind="$attrs"
    :class="[
      'flex items-center gap-2 rounded-lg font-medium shadow-md transition-all duration-300',
      variantClasses,
      sizeClasses,
    ]"
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
import { computed } from 'vue'

interface Props {
  label?: string
  iconName?: string
  variant?: 'primary' | 'secondary' | 'danger' | 'ghost' | 'warning'
  size?: 'sm' | 'md' | 'lg'
}

const props = withDefaults(defineProps<Props>(), {
  label: 'Konsultasi',
  variant: 'primary',
  size: 'md',
})

const variantClasses = computed(() => {
  switch (props.variant) {
    case 'secondary':
      return 'bg-gray-200 text-gray-800 hover:bg-gray-300 dark:bg-gray-700 dark:text-white dark:hover:bg-gray-600'
    case 'danger':
      return 'bg-red-600 text-white hover:bg-red-700'
    case 'ghost':
      return 'bg-transparent text-gray-800 hover:bg-gray-100 dark:text-white dark:hover:bg-gray-800'
    case 'warning':
      return 'bg-yellow-500 text-white hover:bg-yellow-600'
    default:
      return 'bg-green-700 text-white hover:bg-green-800'
  }
})

const sizeClasses = computed(() => {
  switch (props.size) {
    case 'sm':
      return 'px-3 py-1.5 text-xs'
    case 'lg':
      return 'px-6 py-3 text-base'
    default:
      return 'px-4 py-2 text-sm'
  }
})
</script>