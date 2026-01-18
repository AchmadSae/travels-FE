<template>
  <div>
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-8">
      <HomeBio />
      <LazyHomeBenefit hydrate-on-visible />
    </div>
    <LazyHomeFeedback hydrate-on-visible />
    <LazyHomeBantuan hydrate-on-visible />
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default',
  // style: {
  //   backgroundImage: `url('/bg-home-1.webp')`,
  //   backgroundSize: 'contain',
  //   backgroundPosition: 'top',
  //   backgroundRepeat: 'no-repeat',
  // },
})
</script>

<style scoped>

</style>
