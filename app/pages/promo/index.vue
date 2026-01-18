<template>
  <div class="">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-8">
      <div class="flex flex-col gap-7 pt-36 md:pb-36 md:pt-60 items-center justify-center">
        <div class="text-2xl text-center md:text-4xl font-bold text-white md:max-w-md">
          Wujudkan Liburan Islamic Bersama Kami
        </div>
        <div class="flex max-sm:w-full">
          <PromoSearch />
        </div>
      </div>
    </div>
    <div class="md:max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-8">
      <div class="grid gap-8 grid-cols-1 md:grid-cols-3 place-items-center place-content-center justify-center items-center">
        <!-- <PromoItem
          v-for="value in [1, 1, 1, 1, 1, 1, 1]"
          :key="value"
          category="UMROH EXCLUSIVE"
          title="Ramadhan Karim Promo Discount"
          price="254.99"
          image-src="https://callistatour.com/data/img/tour/37f7c82f-2a27-4718-8461-79ecda53e57a.jpg"
          :details="detailPaket"
        /> -->
        <PromoCard
          v-for="value in [1, 1, 1, 1, 1, 1, 1]"
          :key="value"
          :title="promoData.title"
          :discount-percentage="promoData.discountPercentage"
          :original-price="promoData.originalPrice"
          :discounted-price="promoData.discountedPrice"
          :features="promoData.features"
          :image="promoData.image"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default',
  style: {
    backgroundImage: `url('/bg-promo.webp')`,
    backgroundSize: 'cover',
    backgroundPosition: 'center',
  },
  class: 'bg-gradient-to-b from-white to-[#414D55]',
})
const detailPaket = [
  { label: 'Paket', value: 'Reguler' },
  { label: 'Lama', value: '7 hari' },
  { label: 'Quantity', value: '1 Orang' },
  { label: 'Destinasi', value: 'Madinah' },
]
const promoData = {
  title: 'Ziarah Makam Walisongo',
  discountPercentage: '10%',
  originalPrice: 'Rp. 4.000.000,00',
  discountedPrice: 'Rp. 3.000.000,00',
  features: [
    'Akomodasi konsumsi',
    'Bag travels',
    'Kitab Doa',
  ],
  // Pastikan URL gambar valid
  image: '/detail_1.png',
}
</script>

<style scoped>

</style>
