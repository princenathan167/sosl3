<script setup>
import { ref } from 'vue'

const attractions = ref([
  {
    name: 'Volcanoes National Park',
    description: 'Home to mountain gorillas, bamboo forests, and misty volcano peaks for unforgettable trekking experiences.'
  },
  {
    name: 'Musanze Caves',
    description: 'Ancient caves hidden beneath limestone hills, ideal for guided exploration and learning about local geology.'
  },
  {
    name: 'Lake Ruhondo',
    description: 'A serene crater lake perfect for lakeside walks, birdwatching, and peaceful sunsets.'
  },
  {
    name: 'Kinigi Village',
    description: 'A cultural gateway to the northern region with local markets, traditional crafts, and nearby hiking trails.'
  }
])
</script>

<template>
  <div class="page bg-white rounded-lg shadow-lg p-8">
    <div class="header-section mb-8">
      <h1 class="text-4xl font-bold text-green-700 mb-4">Northern Province</h1>
      <p class="text-lg text-gray-800 leading-relaxed">
        The Northern Province features rugged mountains, volcanic landscapes, and famous gorilla trekking destinations. It is a region of dramatic scenery, wildlife conservation, and vibrant community experiences.
      </p>
    </div>

    <div class="attractions-section">
      <h2 class="text-2xl font-bold text-green-700 mb-6">Key Attractions</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <div
          v-for="(attraction, index) in attractions"
          :key="index"
          class="attraction-card bg-gradient-to-br from-green-50 to-emerald-50 p-6 rounded-lg border-l-4 border-green-600 hover:shadow-lg transition"
        >
          <h3 class="text-xl font-bold text-green-700 mb-2">{{ attraction.name }}</h3>
          <p class="text-gray-600">{{ attraction.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.page {
  animation: fadeIn 0.3s ease-in;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
