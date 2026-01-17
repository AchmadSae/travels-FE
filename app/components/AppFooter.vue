<script setup lang="ts">
const footerMenu = ref([
  {
    title: "Privacy Policy",
    link: "#",
  },
  {
    title: "Terms of Use",
    link: "#",
  },
  {
    title: "Legal",
    link: "#",
  },
  {
    title: "Site Map",
    link: "#",
  },
]);
const tentangKami = ref([
  {
    title: "Paket dan Promo",
    link: "#",
  },
  {
    title: "Berita dan Artikel",
    link: "#",
  },
]);
const contactInfo = [
  {
    type: "phone",
    text: "+123 456 7890",
    icon: "heroicons:phone",
    url: "tel:+1234567890",
  },
  {
    type: "email",
    text: "support@mm.com",
    icon: "heroicons:at-symbol",
    url: "mailto:support@mm.com",
  },
];
const activeIndex = ref<number | null>(0);

const toggle = (index: number) => {
  activeIndex.value = activeIndex.value === index ? null : index;
};
</script>
<template>
  <div class="bg-[#282828] w-full text-white">
    <div
      class="flex flex-col gap-8 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-14 md:pt-10 md:pb-14"
    >
      <div class="grid grid-cols-1 md:grid-cols-3 gap-7 justify-between">
        <div class="col-span-2 flex flex-col gap-4">
          <div>
            <!-- logo here -->
            <span class="text-2xl">Macat Megatrons</span>
          </div>
          <div class="text-sm text-[#EBEBEB] md:max-w-96 mb-4">
            Macat Megatrons is a thriving community where innovators,
            professionals, and enthusiasts come together to share knowledge,
            collaborate, and grow.
          </div>
          <SocialLinks />
          <!-- logo -->
        </div>
        <div
          class="grid grid-cols-2 md:flex md:flex-row gap-10 md:justify-center"
        >
          <div class="flex flex-col gap-2 w-full">
            <div class="text-xl">Tentang Kami</div>
            <div class="flex flex-col gap-2">
              <div
                v-for="value in tentangKami"
                :key="value.title"
                class="text-base text-[#EBEBEB]"
              >
                {{ value.title }}
              </div>
            </div>
          </div>
          <div class="flex flex-col gap-2 w-full">
            <div class="text-xl">Contact</div>
            <div class="flex flex-col gap-2">
              <NuxtLink
                v-for="(contact, index) in contactInfo"
                :key="index"
                :href="contact.url"
                class="flex items-center gap-2 group text-base text-[#EBEBEB]"
              >
                <Icon
                  :name="contact.icon"
                  class="w-6 h-6 text-[#608AF5] transition-transform duration-300 group-hover:scale-110"
                />

                <span
                  class="font-normal tracking-wide group-hover:text-[#608AF5] transition-colors duration-300"
                >
                  {{ contact.text }}
                </span>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      class="flex pb-8 max-sm:flex-col gap-2 justify-center text-[#EBEBEB] text-xs items-center"
    >
      <span class=""> © 2025 Macat Megatrons. All rights reserved. </span>
    </div>
  </div>
</template>
