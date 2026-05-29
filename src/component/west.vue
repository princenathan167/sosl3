<script setup>
import { ref } from 'vue'

const attractions = ref([
  { name: 'Lake Kivu Shore', description: 'Relax on scenic lakeshores with boat trips and waterfront villages.' },
  { name: 'Gishwati-Mukura', description: 'Explore recovered forests and conservation projects in western reserves.' },
  { name: 'Scenic Drives', description: 'Winding roads with panoramic views and coffee plantations.' }
])
</script>

<template>
  <main class="page bg-white rounded-lg shadow-lg p-8">
    <div class="header-section mb-8">
      <h1 class="text-4xl font-bold text-green-700 mb-4">Western Province</h1>
      <p class="text-lg text-gray-800 leading-relaxed">
        The Western Province offers dramatic lakeside scenery, recovered forests and unique cultural experiences along Lake Kivu.
      </p>
    </div>

    <div class="attractions-section">
      <h2 class="text-2xl font-bold text-green-700 mb-6">Key Attractions</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <div v-for="(a, i) in attractions" :key="i" class="attraction-card bg-gradient-to-br from-green-50 to-emerald-50 p-6 rounded-lg border-l-4 border-green-600">
          <h3 class="text-xl font-bold text-green-700 mb-2">{{ a.name }}</h3>
          <p class="text-gray-800">{{ a.description }}</p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.page { animation: fadeIn 0.3s ease-in; }
@keyframes fadeIn { from { opacity:0; transform:translateY(10px);} to { opacity:1; transform:translateY(0);} }
</style>
