<script setup>
import { ref } from 'vue'

const attractions = ref([
  {
    name: 'Akagera National Park',
    description: 'Rwanda\'s largest national park featuring abundant wildlife including lions, elephants, buffalo, and giraffes. Perfect for safari adventures.'
  },
  {
    name: 'Lake Muhazi',
    description: 'A serene lake offering beautiful scenery, water sports, and opportunities for bird watching and relaxation.'
  },
  {
    name: 'Kayonza District',
    description: 'Known for its rolling hills, agricultural landscapes, and warm hospitality. Experience authentic rural Rwanda life.'
  },
  {
    name: 'Ngezi Forest',
    description: 'A pristine forest reserve perfect for nature walks, bird watching, and experiencing Rwanda\'s natural beauty up close.'
  }
])
</script>

<template>
  <main class="page bg-white rounded-lg shadow-lg p-8">
    <div class="header-section mb-8">
      <h1 class="text-4xl font-bold text-green-700 mb-4">Eastern Province</h1>
      <p class="text-lg text-gray-800 leading-relaxed">
        The Eastern Province is Rwanda's gateway to adventure and wildlife encounters. Home to the magnificent Akagera National Park, 
        this region offers thrilling safari experiences, pristine natural landscapes, and a glimpse into Rwanda's untamed wilderness. 
        It's the perfect destination for nature lovers and adventure enthusiasts.
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
  </main>
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
