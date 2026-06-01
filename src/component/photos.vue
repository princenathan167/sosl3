<script setup>
import { ref } from 'vue'
import bg from '../assets/bg.jpg'
import homeImg from '../assets/home.jpg'
import serviceImg from '../assets/service.jpg'

const album = ref([
  { id: 1, src: bg, title: 'Volcanic Landscapes', desc: 'The majestic peaks of the Northern Province.' },
  { id: 2, src: homeImg, title: 'Rwandan Hospitality', desc: 'Experience the warm welcome of our people.' },
  { id: 3, src: serviceImg, title: 'Tourism Services', desc: 'Expert guidance for your mountain adventures.' },
  { id: 4, src: bg, title: 'Green Countryside', desc: 'The hills that give Rwanda its famous name.' }
])
</script>

<template>
  <div class="page bg-white rounded-lg shadow-lg p-8">
    <div class="header-section mb-8 border-b border-emerald-100 pb-6">
      <h1 class="text-4xl font-bold text-green-700 mb-4">Photo Gallery</h1>
      <p class="text-lg text-gray-800">Visual highlights of Tembera Rwanda through our lens.</p>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <div v-for="photo in album" :key="photo.id" class="group rounded-xl overflow-hidden border border-emerald-100 shadow-sm">
        <div class="h-64 overflow-hidden relative">
          <img :src="photo.src" class="w-full h-full object-cover transition duration-500 group-hover:scale-110" />
        </div>
        <div class="p-6">
          <h3 class="text-xl font-bold text-green-800 mb-2">{{ photo.title }}</h3>
          <p class="text-gray-600 text-sm">{{ photo.desc }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.page { animation: fadeIn 0.4s ease-out; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
</style>
