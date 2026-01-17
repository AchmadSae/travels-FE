<script setup>
import { ref } from 'vue'

const emit = defineEmits(['close'])

const form = ref({
  nama: '',
  tanggalLahir: '',
  telepon: '',
  email: '',
  voucher: '',
  catatan: '',
  setuju: false,
})

const submitForm = () => {
  if (!form.value.setuju) {
    alert('Mohon setujui syarat dan ketentuan.')
    return
  }
  // Logic submit di sini
  emit('close')
}
</script>

<template>
  <Teleport to="body">
    <Transition
      enter-active-class="transition duration-300 ease-[cubic-bezier(0.16,1,0.3,1)]"
      enter-from-class="opacity-0 translate-y-8 scale-90"
      enter-to-class="opacity-100 translate-y-0 scale-100"
      leave-active-class="transition duration-200 ease-in"
      leave-from-class="opacity-100 translate-y-0 scale-100"
      leave-to-class="opacity-0 translate-y-8 scale-90"
    >
      <div
        class="fixed inset-0 z-[9999] flex items-center justify-center p-4 bg-black/60 backdrop-blur-sm"
        @click.self="$emit('close')"
      >
        <div class="bg-white rounded-xl shadow-2xl w-full max-w-4xl overflow-hidden relative max-h-[90vh] overflow-y-auto transform-gpu">
          <button
            class="absolute top-4 right-4 text-gray-400 hover:text-gray-600 transition z-10 p-1 rounded-full hover:bg-gray-100"
            @click="$emit('close')"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="2"
              stroke="currentColor"
              class="w-6 h-6"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>

          <div class="pt-8 pb-4 px-8 border-b border-gray-100">
            <h2 class="text-2xl font-bold text-gray-600 text-center tracking-wide uppercase">
              DATA PEMESANAN
            </h2>
          </div>

          <div class="p-8">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-5 mb-6">
              <div>
                <input
                  v-model="form.nama"
                  type="text"
                  placeholder="Nama Jamaah"
                  class="w-full border border-blue-400 rounded-lg px-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition"
                >
              </div>
              <div class="relative">
                <input
                  v-model="form.tanggalLahir"
                  type="text"
                  placeholder="Tanggal Lahir"
                  onfocus="(this.type='date')"
                  onblur="(this.type='text')"
                  class="w-full border border-blue-400 rounded-lg px-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition"
                >
              </div>
              <div>
                <input
                  v-model="form.telepon"
                  type="tel"
                  placeholder="Nomor Telepone"
                  class="w-full border border-blue-400 rounded-lg px-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition"
                >
              </div>
              <div>
                <input
                  v-model="form.email"
                  type="email"
                  placeholder="Email"
                  class="w-full border border-blue-400 rounded-lg px-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition"
                >
              </div>
            </div>

            <div class="text-center mb-6">
              <p class="text-xs text-gray-500 italic mb-4">
                *Data lebih dari satu, wajib menyertakan nomor affiliasi
              </p>
              <button class="bg-[#EFA63E] hover:bg-orange-500 text-white font-medium py-2 px-6 rounded-lg inline-flex items-center gap-2 shadow-md transition transform active:scale-95">
                <span>+</span> Tambah Jamaah
              </button>
            </div>

            <div class="space-y-6">
              <div class="relative">
                <input
                  v-model="form.voucher"
                  type="text"
                  placeholder="KODE VOUCHER"
                  class="w-full border border-blue-600 rounded-lg px-4 py-3 pr-24 uppercase focus:ring-2 focus:ring-blue-500 outline-none transition"
                >
                <button class="absolute right-2 top-1/2 -translate-y-1/2 bg-[#1E4FD9] hover:bg-blue-800 text-white text-xs font-bold px-5 py-2 rounded transition">
                  REDEEM
                </button>
              </div>
              <textarea
                v-model="form.catatan"
                rows="4"
                placeholder="Catatan Khusus ( optional )"
                class="w-full border border-blue-500 rounded-lg px-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition resize-none"
              />
            </div>

            <div class="flex flex-col md:flex-row justify-between items-center gap-4 mt-8">
              <label class="flex items-center gap-3 cursor-pointer select-none group">
                <input
                  v-model="form.setuju"
                  type="checkbox"
                  class="w-5 h-5 accent-[#D34528] cursor-pointer"
                >
                <span class="text-sm text-gray-500 italic group-hover:text-gray-700 transition">*Setuju dengan Syarat dan Ketentuan</span>
              </label>
              <button
                class="bg-[#566B5C] hover:bg-[#45574a] text-white font-bold py-3 px-8 rounded-lg shadow-lg transition transform hover:-translate-y-0.5 active:scale-95 duration-200"
                @click="submitForm"
              >
                BOOKING
              </button>
            </div>
          </div>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>
