<template>
  <div class="">
    <BookingForm
      v-if="showModal"
      @close="showModal = false"
    />
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 pb-16 md:pb-36 mt-32 md:mt-40">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div
          id="left-sect"
          class="flex flex-col gap-6"
        >
          <div class="text-2xl md:text-4xl font-bold text-[#014F5A]">
            Overview Paket
          </div>
          <div class="text-[#667085] flex flex-col gap-4">
            <span>
              A modern UI Kit for building custom mapping experiences inspired
              by Google Maps. Includes pre-made components, styles, and screen
              variations for seamless design customization.
            </span>
            <span>
              A modern UI Kit for building custom mapping experiences inspired
              by Google Maps. Includes pre-made components, styles, and screen
              variations for seamless design customization.
            </span>
          </div>
          <div class="flex justify-center my-10">
            <BaseButton
              label="Daftar Sekarang"
              class="py-4 px-4"
              icon-name="fluent:airplane-take-off-24-regular"
              @click="showModal = true"
            />
          </div>
          <div class="flex flex-col gap-4">
            <div class="text-2xl md:text-4xl font-bold text-[#014F5A]">
              Persyaratan & Ketentuan
            </div>
            <ul class="list-disc pl-5 text-[#667085]">
              <li
                v-for="syarat in persyaratan"
                :key="syarat"
              >
                {{ syarat }}
              </li>
            </ul>
          </div>
        </div>
        <div id="right-sect">
          <div class="flex flex-col gap-4">
            <NuxtImg
              src="/detail_1.png"
              alt="/detail_1.png"
              loading="lazy"
              class="w-full h-full object-cover rounded-lg shadow-lg transition-transform duration-500 group-hover:scale-105"
              width="500"
              height="500"
              format="webp"
            />
            <div class="flex flex-col md:flex-row gap-4">
              <NuxtImg
                src="/detail_2.png"
                alt="/detail_2.png"
                loading="lazy"
                class="w-full h-full object-cover rounded-lg shadow-lg transition-transform duration-500 group-hover:scale-105"
                width="500"
                height="500"
                format="webp"
              />
              <NuxtImg
                src="/detail_3.png"
                alt="/detail_3.png"
                loading="lazy"
                class="w-full h-full object-cover rounded-lg shadow-lg transition-transform duration-500 group-hover:scale-105"
                width="500"
                height="500"
                format="webp"
              />
            </div>
          </div>
        </div>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-8">
        <div>
          <div class="w-full h-8 md:h-10 bg-[#46715F] mb-4" />
          <div class="flex flex-col gap-4">
            <div class="text-2xl md:text-4xl font-bold text-[#014F5A]">
              Biaya Termasuk
            </div>
            <ul class="list-disc pl-5 text-[#667085]">
              <li
                v-for="termasuk in biayaTermasuk"
                :key="termasuk"
              >
                {{ termasuk }}
              </li>
            </ul>
          </div>
        </div>
        <div>
          <div class="w-full h-8 md:h-10 bg-[#D32600] mb-4" />
          <div class="flex flex-col gap-4">
            <div class="text-2xl md:text-4xl font-bold text-[#014F5A]">
              Biaya Tidak Termasuk
            </div>
            <ul class="list-disc pl-5 text-[#667085]">
              <li
                v-for="tidakTermasuk in biayaTidakTermasuk"
                :key="tidakTermasuk"
              >
                {{ tidakTermasuk }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default',
  class: 'bg-white',
})
const showModal = ref(false)
const persyaratan = [
  'Pas Foto background putih, ukuran 4 x 6 = 7 lembar',
  'Paspor asli dengan nama 2 kata, contoh: Mohammad Abdul (paspor berlaku minimal 12 bulan saat keberangkatan)',
  'Buku Kuning ICV (Suntik Meningitis dan Polio)',
  'Fotokopi KTP berwarna',
  'Fotokopi Kartu Keluarga',
  'Fotokopi Buku Nikah berwarna bagi yang berangkat suami–istri',
  'Fotokopi Akte Kelahiran berwarna bagi yang berangkat anak / wanita 65 tahun disarankan didampingi pihak keluarga',
  'Menyerahkan DP sebesar Rp 10.000.000 (pelunasan 30 hari sebelum keberangkatan beserta persyaratan poin 1–8)',
  'Fotokopi Kartu Asuransi BPJS (opsional)',
]
const biayaTermasuk = [
  'Tiket pesawat ekonomi PP',
  'Visa Umroh',
  'Visa tambahan negara yang dikunjungi (bagi jamaah yang mengambil paket Umroh Plus)',
  'Government Free Visa',
  'Asuransi visa Umroh',
  'Tour ziarah ke Kota Mekah dan Madinah (apabila diizinkan otoritas setempat)',
  'Transportasi bus full AC selama perjalanan',
  'Akomodasi hotel dan penginapan setaraf',
  'Makan 3 kali sehari',
  'Pembimbing ibadah dan muthawif (guide) yang berpengalaman',
  'Manasik Umroh 1 kali di Jakarta',
  'Zam-zam 5 liter (jika diizinkan)',
]
const biayaTidakTermasuk = [
  'Pembuatan passport dan dokumen perjalanan lainnya',
  'Kelebihan bagasi (maksimal 25 kg)',
  'Tour atau acara di luar program atas permintaan',
  'Pengeluaran pribadi seperti laundry, tips, telepon, dan lain-lain',
  'Suntik meningitis dan polio',
  'Transportasi dari daerah asal (di luar Jakarta)',
  'Biaya pengiriman perlengkapan',
  'Handling dan perlengkapan sebesar Rp 1.500.000 (mendapatkan koper, tas selempang, batik, mukena/ihrom, dan buku doa)',
]
</script>

<style scoped></style>
