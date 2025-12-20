<template>
  <div class="w-full mx-auto px-4">
    <div class="bg-white rounded-2xl shadow-[0_20px_50px_rgba(0,0,0,0.1)] p-6 md:p-8 flex flex-col lg:flex-row items-end gap-6 border border-gray-50">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 flex-grow w-full">
        <BaseInput
          v-model="model.jumlah"
          label="Jumlah Jamaah"
          type="number"
          placeholder="0"
          required
          custom-label-class="text-lg font-semibold"
        />

        <BaseInput
          v-model="model.tanggal"
          label="Keberangkatan"
          placeholder="Pilih Tanggal"
          custom-label-class="text-lg font-semibold"
        />

        <BaseSelect
          v-model="model.kategori"
          label="Category"
          :options="categories"
          placeholder="Selected Option"
          custom-label-class="text-lg font-semibold"
        />
      </div>

      <BaseButton
        variant="primary"
        size="lg"
        icon="heroicons:magnifying-glass-20-solid"
        class="w-full lg:w-auto py-3"
        @click="$emit('search', model)"
      >
        <span class="text-xl font-bold">Cari</span>
      </BaseButton>
    </div>
  </div>
</template>

<script setup lang="ts">
// Data Model sesuai kebutuhan pencarian
const model = ref({
  jumlah: '',
  tanggal: '',
  kategori: '',
})

const categories = [
  { label: 'Umroh Reguler', value: 'reguler' },
  { label: 'Umroh Plus', value: 'plus' },
  { label: 'Haji Furoda', value: 'furoda' },
]

defineEmits(['search'])
</script>
