<script setup>
import { ref } from 'vue'
defineProps({ currentPage: String })
const emit = defineEmits(['navigate'])

const navItems = [
  { id: 'home', label: 'Home' },
  { id: 'about', label: 'About' },
  { 
    id: 'destination', label: 'Destination',
    children: [
      { id: 'kigali', label: 'Kigali City' },
      { id: 'northern', label: 'Northern Province' },
      { id: 'southern', label: 'Southern Province' },
      { id: 'eastern', label: 'Eastern Province' },
      { id: 'western', label: 'Western Province' }
    ]
  },
  { id: 'service', label: 'Service' },
  {
    id: 'gallery', label: 'Gallery',
    children: [
      { id: 'photos', label: 'Photos' },
      { id: 'videos', label: 'Videos' }
    ]
  },
  { id: 'contact', label: 'Contact' }
]

const selectedLanguage = ref('en')
const navigate = (page) => { emit('navigate', page) }
</script>

<template>
  <nav class="navbar">
    <div class="brand">Tembera Rwanda</div>
    <ul class="links">
      <li v-for="item in navItems" :key="item.id" class="nav-item-container">
        <button @click="navigate(item.id)" :class="{ active: currentPage === item.id }" class="nav-link">
          {{ item.label }} <span v-if="item.children" class="arrow">▾</span>
        </button>
        <ul v-if="item.children" class="dropdown-menu">
          <li v-for="child in item.children" :key="child.id">
            <button @click.stop="navigate(child.id)" class="dropdown-item" :class="{ 'active-sub': currentPage === child.id }">
              {{ child.label }}
            </button>
          </li>
        </ul>
      </li>
    </ul>
    <div class="language-selector">
      <select v-model="selectedLanguage">
        <option value="en">🇬🇧 EN</option>
        <option value="rw">🇷🇼 RW</option>
      </select>
    </div>
  </nav>
</template>

<style scoped>
.navbar { display: flex; justify-content: space-between; align-items: center; padding: 1rem 1.5rem; background: #204d02; color: white; position: relative; z-index: 1000; }
.brand { font-weight: 700; font-size: 1.2rem; }
.links { display: flex; gap: 0.5rem; list-style: none; margin: 0; padding: 0; }
.nav-item-container { position: relative; }
.nav-link { background: none; border: none; color: white; cursor: pointer; padding: 0.55rem 0.85rem; border-radius: 6px; font-weight: 500; display: flex; align-items: center; gap: 4px; transition: 0.3s; }
.nav-link:hover { background-color: rgba(255, 255, 255, 0.15); }
.nav-link.active { background-color: #22c55e; }
.dropdown-menu { display: none; position: absolute; top: 100%; left: 0; min-width: 190px; background: white; border-radius: 8px; box-shadow: 0 10px 15px rgba(0,0,0,0.2); padding: 0; z-index: 1100; border: 1px solid rgba(0,0,0,0.05); }
.nav-item-container:hover .dropdown-menu { display: block; }
.dropdown-menu::before { content: ""; position: absolute; top: -15px; left: 0; width: 100%; height: 15px; }
.dropdown-item { width: 100%; text-align: left; background: white; border: none; padding: 0.75rem 1rem; color: #1f2937; cursor: pointer; }
.dropdown-item:hover { background-color: #f0fdf4; color: #22c55e; }
.active-sub { color: #22c55e; font-weight: 700; background: #f0fdf4; }
</style>
