<script setup>
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

const navigate = (page) => {
  emit('navigate', page)
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
}
.brand {
  font-weight: 700;
  font-size: 1.1rem;
}
.links {
  display: flex;
  gap: 1rem;
  list-style: none;
  margin: 0;
  padding: 0;
}
.nav-link {
  background: none;
  border: none;
  color: #f9fafb;
  text-decoration: none;
  font-weight: 500;
  cursor: pointer;
  padding: 0.5rem 0.75rem;
  border-radius: 4px;
  transition: all 0.3s ease;
}
.nav-link:hover {
  background-color: rgba(255, 255, 255, 0.1);
  color: #60a5fa;
}
.nav-link.active {
  background-color: #22c55e;
  color: #fff;
  font-weight: 600;
}
</style>