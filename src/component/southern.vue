<script setup>
import { ref } from 'vue'

const attractions = ref([
  {
    name: 'Nyungwe Forest National Park',
    description: 'One of Africa\'s oldest and most biodiverse rainforests. Trek through canopy walks and spot chimpanzees, colobus monkeys, and 300+ bird species.'
  },
  {
    name: 'Butare (Huye) Town',
    description: 'Rwanda\'s second city, known as the intellectual capital. Home to the National Museum and vibrant cultural scene.'
  },
  {
    name: 'Gisozi Memorial Site',
    description: 'A powerful historical site dedicated to genocide remembrance with educational exhibits and peaceful gardens.'
  },
  {
    name: 'Lake Muhazi',
    description: 'Pristine waters perfect for swimming, boating, and relaxation with surrounding lush landscapes.'
  }
])
</script>

<template>
  <main class="page bg-white rounded-lg shadow-lg p-8">
    <div class="header-section mb-8">
      <h1 class="text-4xl font-bold text-green-700 mb-4">Southern Province</h1>
      <p class="text-lg text-gray-800 leading-relaxed">
        The Southern Province offers a perfect blend of natural wonders and cultural significance. From the ancient rainforests 
        of Nyungwe to historical landmarks and peaceful lakeside towns, this region provides a diverse range of experiences that 
        showcase Rwanda's rich history, biodiversity, and warm hospitality.
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
