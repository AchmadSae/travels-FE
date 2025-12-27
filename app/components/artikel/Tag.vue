<script setup lang="ts">
// Kita definisikan props agar data tags bisa diganti dari luar komponen
interface Props {
  title?: string;
  tags?: string[];
}

// Default values sesuai dengan screenshot
const props = withDefaults(defineProps<Props>(), {
  title: 'All Tags',
  tags: () => [
    'Business', 
    'Experience', 
    'Screen', 
    'Technology', 
    'Marketing', 
    'Life'
  ],
});

const emit = defineEmits(['click-tag']);

function handleTagClick(tag: string) {
  emit('click-tag', tag);
}
</script>

<template>
  <section class="w-full py-12 px-6 flex justify-center items-center">
    <div class="max-w-2xl w-full">
      
      <h2 class="text-2xl md:text-4xl font-bold text-[#2d2a3e] mb-8">
        All Tags
      </h2>

      <div class="flex flex-wrap gap-4 md:gap-6">
        <button
          v-for="(tag, index) in tags"
          :key="index"
          @click="handleTagClick(tag)"
          class="
            px-4 py-2
            text-sm 
            rounded-full 
            border-2 border-gray-500 
            text-gray-700 font-bold 
            bg-transparent 
            transition-all duration-300 ease-in-out
            hover:bg-gray-700 hover:border-gray-700 hover:text-white hover:scale-105
            focus:outline-none focus:ring-2 focus:ring-gray-400 focus:ring-offset-2
          "
        >
          {{ tag }}
        </button>
      </div>

    </div>
  </section>
</template>