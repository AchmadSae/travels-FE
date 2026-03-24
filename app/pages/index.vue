<template>
  <div class="wrapper">
    <header>
      <img src="/paralax_3.png" alt="" srcset="" class="background">
      <img src="/paralax_2.png" alt="" srcset="" class="middle">
      <img src="/paralax_1.png" alt="" srcset="" class="foreground">
      <h1 class="title">السلام عليكم ورحمة الله وبركاته</h1><br>
    </header>
    <section ref="navWhiteWhenScroll">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-5 pb-10">
        <HomeBio />
        <LazyHomeBenefit hydrate-on-visible />
      </div>
      <LazyHomeFeedback hydrate-on-visible />
      <LazyHomeBantuan hydrate-on-visible />
      <LazyAppFooter hydrate-on-visible />
    </section>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default',
})
</script>

<style scoped>
  body {
      margin: 0;
    }

  .wrapper {
    height: 100vh;
    overflow-y: auto;
    overflow-x: hidden;
    perspective: 15px;
  }

  header {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    transform-style: preserve-3d;
    z-index: -1;
  }

  .background {
    transform: translateZ(-15px) scale(2.5);
  }
  .middle {
    transform: translateZ(-10px) scale(2);
  }
  .foreground {
    transform: translateZ(-5.5px) scale(1.6);
  }

  .background,
  .foreground , .middle{
    position: absolute;
    height: 100%;
    width: 100%;
    object-fit: cover;
    z-index: -1;
  }

  .title {
    font-size:3.5rem;
    color: white;
    text-shadow: 0 0 5px #F8A401;
  }
  section {
    background-color: #35312a;
    color: white;
  }
</style>
