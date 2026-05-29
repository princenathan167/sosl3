<script setup>
// Fixed path: changed from '../../' to '../' to properly target the src/assets folder
import destinationImg from '../assets/bg.jpg'
const emit = defineEmits(['navigate'])

const directions = [
    { key: 'north', label: 'North', desc: 'Explore highland forests and mountain trails in the northern region.' },
    { key: 'east', label: 'East', desc: 'Visit rolling plains, lakes, and cultural villages in the east.' },
    { key: 'south', label: 'South', desc: 'Discover lush valleys and community projects in the south.' },
    { key: 'west', label: 'West', desc: 'See lakeshores, wildlife reserves, and scenic drives in the west.' }
]

const preview = (d) => d.desc
</script>

<template>
    <main class="page space-y-10">
        <div class="rounded-[2rem] bg-white border border-emerald-100 shadow-2xl p-8">
            <div class="grid gap-8 lg:grid-cols-[1.4fr_1fr] items-center">
                <div>
                    <p class="text-sm uppercase tracking-[0.35em] text-emerald-700">Destinations</p>
                    <h1 class="text-4xl font-bold text-green-700 mb-4">Choose a region to explore</h1>
                    <p class="text-lg text-gray-700 leading-relaxed">
                        Select a direction to open a dedicated page for that region and learn about highlights, attractions, and travel tips.
                    </p>
                </div>
                <div class="rounded-[2rem] overflow-hidden shadow-xl border border-emerald-100">
                    <img :src="destinationImg" alt="Rwanda destination" class="w-full h-80 object-cover" />
                </div>
            </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
            <article v-for="d in directions" :key="d.key" class="p-6 bg-emerald-50 rounded-3xl shadow-sm border border-emerald-100 hover:shadow-lg transition">
                <h2 class="text-xl font-semibold text-green-700 mb-2">{{ d.label }}</h2>
                <p class="text-gray-600 mb-4">{{ preview(d) }}</p>
                <button @click="() => emit('navigate', d.key)" class="px-4 py-2 bg-green-600 text-white rounded hover:bg-green-700">Open Page</button>
            </article>
        </div>
    </main>
</template>