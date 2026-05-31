<script setup>
import { ref } from 'vue'

defineProps({
  currentPage: String
})

const emit = defineEmits(['navigate'])

const navItems = [
  { id: 'home', label: 'Home' },
  { id: 'about', label: 'About' },
  { id: 'destination', label: 'Destination' },
  { id: 'service', label: 'Service' },
  { id: 'contact', label: 'Contact' }
]

const selectedLanguage = ref('en')

const navigate = (page) => {
  emit('navigate', page)
}

const changeLanguage = () => {
  console.log(`Language changed to: ${selectedLanguage.value}`)
}
</script>

<template>
  <nav class="navbar">
    <div class="brand">Tembera Rwanda</div>

    <ul class="links">
      <li v-for="item in navItems" :key="item.id">
        <button
          @click="navigate(item.id)"
          :class="{ active: currentPage === item.id }"
          class="nav-link"
        >
          {{ item.label }}
        </button>
      </li>
    </ul>

    <div class="language-selector">
      <select
        v-model="selectedLanguage"
        @change="changeLanguage"
      >
        <option value="en">🇬🇧 English</option>
        <option value="rw">🇷🇼 Kinyarwanda</option>
        <option value="fr">🇫🇷 Français</option>
      </select>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 1.5rem;
  background: #204d02;
  color: #f9fafb;
  flex-wrap: wrap;
  gap: 1rem;
}

.brand {
  font-weight: 700;
  font-size: 1.2rem;
  letter-spacing: 0.5px;
}

.links {
  display: flex;
  gap: 1rem;
  list-style: none;
  margin: 0;
  padding: 0;
  flex-wrap: wrap;
}

.nav-link {
  background: none;
  border: none;
  color: #f9fafb;
  font-weight: 500;
  cursor: pointer;
  padding: 0.55rem 0.85rem;
  border-radius: 6px;
  transition: all 0.3s ease;
}

.nav-link:hover {
  background-color: rgba(255, 255, 255, 0.15);
  color: #ffffff;
}

.nav-link.active {
  background-color: #22c55e;
  color: #ffffff;
  font-weight: 600;
}

.language-selector {
  display: flex;
  align-items: center;
}

.language-selector select {
  background: #ffffff;
  color: #204d02;
  border: none;
  border-radius: 6px;
  padding: 0.55rem 0.85rem;
  font-size: 0.95rem;
  font-weight: 600;
  cursor: pointer;
  outline: none;
  transition: all 0.3s ease;
}

.language-selector select:hover {
  transform: translateY(-1px);
}

.language-selector select:focus {
  box-shadow: 0 0 0 3px rgba(34, 197, 94, 0.3);
}

@media (max-width: 768px) {
  .navbar {
    flex-direction: column;
    text-align: center;
  }

  .links {
    justify-content: center;
  }
}
</style>