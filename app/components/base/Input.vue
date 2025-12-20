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

    <input
      :id="id"
      :type="type"
      :value="modelValue"
      :placeholder="placeholder"
      :required="required"
      class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-600 focus:border-transparent transition-all duration-200"
      @input="updateValue"
    />
  </div>
</template>

<script setup lang="ts">
// Menggunakan interface agar tidak ada lagi parsing error di ESLint
interface Props {
  modelValue: string | number
  label?: string
  id?: string
  type?: string
  placeholder?: string
  required?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  label: '',
  id: () => `input-${Math.random().toString(36).current?.slice(2, 9)}`,
  type: 'text',
  placeholder: '',
  required: false
})

const emit = defineEmits(['update:modelValue'])

const updateValue = (event: Event) => {
  const target = event.target as HTMLInputElement
  emit('update:modelValue', target.value)
}
</script>