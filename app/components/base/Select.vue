<template>
  <div class="w-full">
    <label 
      v-if="label" 
      :for="id" 
      class="block font-medium text-slate-900 mb-3"
    >
      {{ label }}
      <span v-if="required" class="text-red-500 ml-1">*</span>
    </label>

    <div class="relative">
      <select
        :id="id"
        :value="modelValue"
        :required="required"
        class="w-full appearance-none px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-600 focus:border-transparent transition-all duration-200 bg-white pr-12 cursor-pointer"
        @change="updateValue"
      >
        <option value="" disabled selected>{{ placeholder }}</option>
        <option 
          v-for="option in options" 
          :key="option.value" 
          :value="option.value"
        >
          {{ option.label }}
        </option>
      </select>

      <div class="absolute inset-y-0 right-0 flex items-center pr-4 pointer-events-none">
        <Icon 
          name="heroicons:chevron-down-20-solid" 
          class="w-8 h-8 text-slate-900" 
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
// Menggunakan interface untuk type-safety sesuai pengalaman TypeScript Anda
interface Option {
  label: string
  value: string | number
}

interface Props {
  modelValue: string | number
  options: Option[]
  label?: string
  id?: string
  placeholder?: string
  required?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  label: '',
  id: () => `select-${Math.random().toString(36).slice(2, 9)}`,
  placeholder: 'Selected Option',
  required: false
})

const emit = defineEmits(['update:modelValue'])

const updateValue = (event: Event) => {
  const target = event.target as HTMLSelectElement
  emit('update:modelValue', target.value)
}
</script>