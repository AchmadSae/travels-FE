<script setup lang="ts">
/**
 * Definisi Tipe Data Agent
 */
interface AgentProps {
  name: string;
  image: string;
  location: string;
  phone: string;
  hours: string;
  additionalInfo?: {
    label: string;
    value: string;
  };
}

const props = defineProps<{
  agent: AgentProps;
}>();
</script>

<template>
  <div class="w-full max-w-sm bg-white rounded-xl shadow-lg border border-gray-100 overflow-hidden flex flex-col">
    
    <div class="px-5 py-4 bg-white border-b border-gray-50">
      <h2 class="text-xl font-bold text-gray-700 truncate">
        {{ agent.name }}
      </h2>
    </div>

    <div class="w-full h-48 relative bg-gray-100 group">
      <NuxtImg
        v-if="agent.image"
        :src="agent.image"
        :alt="agent.name"
        class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
        loading="lazy"
        placeholder
      />
      <div v-else class="w-full h-full flex items-center justify-center text-gray-400">
        <Icon name="heroicons:photo" class="w-12 h-12" />
      </div>
    </div>

    <div class="p-5 space-y-5">
      
      <div class="flex items-start gap-4">
        <Icon name="heroicons:map" class="w-6 h-6 text-green-600 flex-shrink-0 mt-0.5" />
        <span class="text-gray-800 font-medium text-lg leading-snug">
          {{ agent.location }}
        </span>
      </div>

      <div class="flex items-center gap-4">
        <Icon name="heroicons:phone" class="w-6 h-6 text-green-600 flex-shrink-0" />
        <span class="text-gray-800 font-medium text-lg">
          {{ agent.phone }}
        </span>
      </div>

      <div class="flex items-start gap-4">
        <Icon name="heroicons:clock" class="w-6 h-6 text-green-600 flex-shrink-0 mt-0.5" />
        <span class="text-gray-800 font-medium text-lg leading-snug">
          {{ agent.hours }}
        </span>
      </div>
    </div>

    <div class="h-px bg-gray-200 mx-5"></div>

    <div class="p-5 pt-4 bg-gray-50/50">
      <p class="text-blue-400 font-semibold mb-1 text-sm">
        Additional Information:
      </p>
      <div class="text-gray-600 text-sm leading-relaxed">
        <span class="font-bold text-gray-800" v-if="agent.additionalInfo?.label">
          {{ agent.additionalInfo.label }}:
        </span>
        {{ agent.additionalInfo?.value }}
      </div>
    </div>

  </div>
</template>