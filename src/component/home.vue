<script setup>
// Fixed the path: removed one level of ../ 
// This assumes your structure is src/assets/home.jpg and src/component/home.vue
import homeImg from '../assets/home.jpg'
</script>

<template>
  <main class="page">
    <div class="rounded-[2rem] bg-white/90 border border-emerald-100 shadow-2xl backdrop-blur-xl p-10 max-w-5xl mx-auto">
      <div class="grid gap-8 lg:grid-cols-[1.4fr_1fr] items-center">
        
        <!-- Text Content -->
        <div class="space-y-6">
          <p class="text-sm uppercase tracking-[0.4em] text-emerald-700">Explore Rwanda</p>
          <h1 class="text-5xl font-bold text-slate-900 leading-tight">
            Discover Rwanda's natural beauty and local culture.
          </h1>
          <p class="text-lg text-slate-700 leading-relaxed">
            Browse destinations, learn about local services, and plan your trip with our curated experiences designed to make every journey memorable.
          </p>
          
          <div class="grid gap-4 sm:grid-cols-2">
            <div class="rounded-3xl bg-emerald-50 p-5 shadow-sm border border-emerald-100">
              <h2 class="text-xl font-semibold text-green-700 mb-2">Curated itineraries</h2>
              <p class="text-gray-600">Tailored experiences for nature lovers, families, and adventure travelers.</p>
            </div>
            <div class="rounded-3xl bg-emerald-50 p-5 shadow-sm border border-emerald-100">
              <h2 class="text-xl font-semibold text-green-700 mb-2">Local guides</h2>
              <p class="text-gray-600">Connect with experts who share stories, culture, and hidden gems.</p>
            </div>
          </div>
        </div>

        <!-- Image Container -->
        <div class="rounded-[2rem] overflow-hidden shadow-xl border border-emerald-100">
          <!-- The :src="homeImg" now points to the correctly resolved file -->
          <img :src="homeImg" alt="Rwandan landscape" class="w-full h-96 object-cover" />
        </div>

      </div>
    </div>
  </main>
</template>