<script setup>
import { ref } from 'vue'

const videos = ref([
  {
    id: 1,
    title: 'The Rwanda Intore Dance',
    desc: 'The famous "Warrior Dance" is a majestic performance mimicking a battle, complete with traditional spears and lion-mane headpieces.',
    embedUrl: 'https://youtube.com',
    youtubeUrl: 'https://www.youtube.com/watch?v=jzAkiG1O6j4'
  },
  {
    id: 2,
    title: 'Land of a Thousand Hills',
    desc: 'A visual journey through Rwanda’s dramatic vistas, sounds of nature, and the progress of its friendly, committed people.',
    embedUrl: 'https://youtube.com',
    youtubeUrl: 'https://www.youtube.com/watch?v=bX_wOIZW1RM'
  },
  {
    id: 3,
    title: 'Discover Rwanda: Cultural Gems',
    desc: 'Exploring beyond the mountains to find artisan basket weaving, world-class tea, and authentic community experiences.',
    embedUrl: 'https://youtube.com',
    youtubeUrl: 'https://www.youtube.com/watch?v=FyLkD-5s2X4'
  }
])
</script>

<template>
  <div class="page bg-white rounded-lg shadow-lg p-8">
    <div class="header-section mb-8 border-b border-emerald-100 pb-6">
      <h1 class="text-4xl font-bold text-green-700 mb-4">Cultural Video Gallery</h1>
      <p class="text-lg text-gray-800 leading-relaxed">
        Experience the heart of Rwanda through these curated highlights of our tradition and progress.
      </p>
    </div>

    <div class="grid grid-cols-1 gap-12">
      <div v-for="video in videos" :key="video.id" class="video-card bg-emerald-50 rounded-2xl overflow-hidden border border-emerald-100 shadow-sm transition hover:shadow-md">
        <!-- YouTube Responsive Embed -->
        <div class="relative w-full h-0 pb-[56.25%] bg-black">
          <iframe 
            class="absolute top-0 left-0 w-full h-full"
            :src="video.embedUrl" 
            title="YouTube video player" 
            frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
            allowfullscreen
          ></iframe>
        </div>
        
        <div class="p-6">
          <h3 class="text-2xl font-bold text-green-800 mb-2">{{ video.title }}</h3>
          <p class="text-gray-600 leading-relaxed mb-6">{{ video.desc }}</p>
          
          <!-- NEW: Direct YouTube Link -->
          <a 
            :href="video.youtubeUrl" 
            target="_blank" 
            class="inline-flex items-center text-emerald-600 font-bold hover:text-emerald-700 transition"
          >
            Watch on YouTube
            <span class="ml-2">↗</span>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.page { animation: fadeIn 0.5s ease-out; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(15px); } to { opacity: 1; transform: translateY(0); } }
.video-card { transition: transform 0.3s ease; }
.video-card:hover { transform: translateY(-5px); }
</style>
