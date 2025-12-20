<template>
  <div class="bg-gray-400">
    <AppHeader />
    <main>
      <slot />
    </main>
    <LazyAppFooter hydrate-on-visible="" />
  </div>
</template>
