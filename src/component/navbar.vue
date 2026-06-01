<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
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

// Language Selector Logic
const isLangOpen = ref(false)
const selectedLanguage = ref({ code: 'en', label: 'English', flag: '🇬🇧' })
const languages = [
  { code: 'en', label: 'English', flag: '🇬🇧' },
  { code: 'rw', label: 'Kinyarwanda', flag: '🇷🇼' },
  { code: 'fr', label: 'Français', flag: '🇫🇷' }
]

const selectLanguage = (lang) => {
  selectedLanguage.value = lang
  isLangOpen.value = false
}

const navigate = (page) => { emit('navigate', page) }

// Close dropdown when clicking outside
const closeLang = (e) => {
  if (!e.target.closest('.language-selector')) isLangOpen.value = false
}
onMounted(() => window.addEventListener('click', closeLang))
onUnmounted(() => window.removeEventListener('click', closeLang))
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

    <!-- Modern Language Selector -->
    <div class="language-selector">
      <button @click.stop="isLangOpen = !isLangOpen" class="lang-btn">
        <span>{{ selectedLanguage.flag }}</span>
        <span class="lang-label">{{ selectedLanguage.code.toUpperCase() }}</span>
        <span class="arrow" :class="{ rotate: isLangOpen }">▾</span>
      </button>

      <transition name="fade">
        <ul v-if="isLangOpen" class="lang-dropdown scrollbar-custom">
          <li v-for="lang in languages" :key="lang.code">
            <button @click="selectLanguage(lang)" class="lang-option" :class="{ selected: selectedLanguage.code === lang.code }">
              <span class="flag-icon">{{ lang.flag }}</span>
              <span class="full-name">{{ lang.label }}</span>
            </button>
          </li>
        </ul>
      </transition>
    </div>
  </nav>
</template>

<style scoped>
/* Main Navbar */
.navbar { display: flex; justify-content: space-between; align-items: center; padding: 0.75rem 2rem; background: #163d01; color: white; position: relative; z-index: 1000; box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1); }
.brand { font-weight: 800; font-size: 1.4rem; letter-spacing: -0.5px; }

/* Navigation Links */
.links { display: flex; gap: 0.25rem; list-style: none; margin: 0; padding: 0; }
.nav-item-container { position: relative; }
.nav-link { background: none; border: none; color: rgba(255, 255, 255, 0.9); cursor: pointer; padding: 0.6rem 1rem; border-radius: 8px; font-weight: 500; display: flex; align-items: center; gap: 6px; transition: all 0.2s ease; }
.nav-link:hover { background-color: rgba(255, 255, 255, 0.1); color: white; }
.nav-link.active { background-color: #22c55e; color: white; }

/* Dropdown General */
.dropdown-menu { display: none; position: absolute; top: 110%; left: 0; min-width: 210px; background: white; border-radius: 12px; box-shadow: 0 10px 25px rgba(0,0,0,0.2); padding: 0.5rem; z-index: 1100; border: 1px solid rgba(0,0,0,0.05); overflow: hidden; }
.nav-item-container:hover .dropdown-menu { display: block; }
.dropdown-item { width: 100%; text-align: left; background: white; border: none; padding: 0.7rem 1rem; color: #374151; cursor: pointer; border-radius: 6px; transition: 0.2s; font-size: 0.95rem; }
.dropdown-item:hover { background-color: #f0fdf4; color: #166534; }
.active-sub { color: #166534; font-weight: 700; background: #dcfce7; }

/* Language Selector Aesthetic */
.language-selector { position: relative; margin-left: 1rem; }
.lang-btn { background: rgba(255, 255, 255, 0.1); border: 1px solid rgba(255, 255, 255, 0.2); color: white; padding: 0.5rem 0.8rem; border-radius: 50px; cursor: pointer; display: flex; align-items: center; gap: 8px; font-weight: 600; transition: 0.3s; }
.lang-btn:hover { background: rgba(255, 255, 255, 0.2); border-color: #22c55e; }
.lang-label { font-size: 0.85rem; }

.lang-dropdown { position: absolute; right: 0; top: calc(100% + 10px); width: 180px; background: white; border-radius: 12px; box-shadow: 0 10px 20px rgba(0,0,0,0.15); list-style: none; padding: 0.4rem; margin: 0; border: 1px solid #e5e7eb; max-height: 250px; overflow-y: auto; }
.lang-option { width: 100%; display: flex; align-items: center; gap: 10px; padding: 0.6rem 0.8rem; border: none; background: transparent; cursor: pointer; border-radius: 8px; transition: 0.2s; color: #4b5563; }
.lang-option:hover { background: #f0fdf4; color: #166534; }
.lang-option.selected { background: #f0fdf4; color: #22c55e; font-weight: 600; }
.flag-icon { font-size: 1.2rem; }

/* Custom Scrollbar for Lang Selector */
.scrollbar-custom::-webkit-scrollbar { width: 5px; }
.scrollbar-custom::-webkit-scrollbar-track { background: transparent; }
.scrollbar-custom::-webkit-scrollbar-thumb { background: #22c55e; border-radius: 10px; }

/* Animations */
.arrow { font-size: 0.7rem; transition: transform 0.3s; opacity: 0.7; }
.rotate { transform: rotate(180deg); }
.fade-enter-active, .fade-leave-active { transition: opacity 0.2s, transform 0.2s; }
.fade-enter-from, .fade-leave-to { opacity: 0; transform: translateY(-10px); }
</style>
