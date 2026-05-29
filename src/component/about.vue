<script setup>
// Fixed path: removed one level of ../ to resolve the import correctly
import aboutImg from '../assets/bg.jpg'
</script>

<template>
  <main class="page">
    <div class="rounded-[2rem] bg-white border border-emerald-100 shadow-2xl p-8 grid gap-10 lg:grid-cols-[1.4fr_1fr] items-center">
      
      <section class="space-y-6">
        <p class="text-sm uppercase tracking-[0.35em] text-emerald-700">About Rwanda Explorer</p>
        <h1 class="text-4xl font-bold text-slate-900">We design authentic travel stories.</h1>
        <p class="text-lg text-slate-700 leading-relaxed">
          We are a small travel collective dedicated to helping visitors discover Rwanda's rich culture, breathtaking landscapes, and warm communities.
          From mountain gorillas to tranquil lakes and vibrant city life, we craft experiences that connect you to the people and places that make Rwanda unique.
        </p>
        
        <div class="grid gap-4 sm:grid-cols-2">
          <div class="rounded-3xl bg-emerald-50 p-5 shadow-sm border border-emerald-100">
            <h2 class="text-xl font-semibold text-green-700 mb-2">Local expertise</h2>
            <p class="text-gray-600">Travel with guides who know the best hidden spots, vibrant markets, and cultural events.</p>
          </div>
          <div class="rounded-3xl bg-emerald-50 p-5 shadow-sm border border-emerald-100">
            <h2 class="text-xl font-semibold text-green-700 mb-2">Sustainable travel</h2>
            <p class="text-gray-600">We partner with communities and eco-friendly providers to keep your adventure both meaningful and responsible.</p>
          </div>
        </div>
      </section>
      
      <div class="rounded-[2rem] overflow-hidden shadow-xl border border-emerald-100">
        <img :src="aboutImg" alt="Rwanda travel" class="w-full h-96 object-cover" />
      </div>

    </div>
  </main>
</template>