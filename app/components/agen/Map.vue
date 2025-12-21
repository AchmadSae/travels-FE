<template>
  <div class="h-96 md:h-[600px] w-full rounded-lg overflow-hidden shadow-2xl border-8 border-white">
    <ClientOnly>
      <LMap
        :zoom="5"
        :center="[-2.5489, 118.0149]"
        :use-global-leaflet="false"
      >
        <LTileLayer
          url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
          attribution="&copy; OpenStreetMap"
          layer-type="base"
          name="OpenStreetMap"
        />

        <LMarker 
          v-for="agent in agents" 
          :key="agent.id" 
          :lat-lng="[agent.lat, agent.lng]"
        >
          <LPopup>
            <div class="p-3 font-sans">
              <h3 class="font-bold text-lg text-emerald-800">{{ agent.name }}</h3>
              <p class="text-sm text-slate-600">{{ agent.address }}</p>
              <button class="mt-2 text-xs bg-emerald-600 text-white px-3 py-1 rounded-full">
                Hubungi Agen
              </button>
            </div>
          </LPopup>
        </LMarker>
      </LMap>

      <template #fallback>
        <div class="w-full h-full bg-gray-100 animate-pulse flex items-center justify-center text-slate-400">
          Memuat Peta Agen...
        </div>
      </template>
    </ClientOnly>
  </div>
</template>

<script setup lang="ts">
// Tidak perlu import LMap, LTileLayer, dll. Sudah auto-import!
const agents = ref([
  { id: 1, name: 'Pusat Jakarta', lat: -6.2088, lng: 106.8456, address: 'Sudirman Central Business District' },
  { id: 2, name: 'Cabang Surabaya', lat: -7.2575, lng: 112.7521, address: 'Gubeng, Kota Surabaya' },
  { id: 3, name: 'Cabang Makassar', lat: -5.1476, lng: 119.4327, address: 'Panakkukang, Makassar' }
]);
</script>