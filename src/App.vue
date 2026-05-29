<script setup>
import { computed, ref } from 'vue'
import Navbar from './component/navbar.vue'
import Home from './component/home.vue'
import About from './component/about.vue'
import Destination from './component/destination.vue'
import Service from './component/service.vue'
import Contact from './component/contact.vue'
import Footer from './views/footer.vue'
import Northern from './component/northern.vue'
import Eastern from './component/eastern.vue'
import Southern from './component/southern.vue'
import Western from './component/west.vue'
import bg from './assets/bg.jpg'

const currentPage = ref('home')
const wrapperStyle = computed(() => currentPage.value === 'home'
  ? { backgroundImage: `url(${bg})`, backgroundSize: 'contain', backgroundPosition: 'center', backgroundRepeat: 'no-repeat' }
  : {})

const pages = {
  home: { component: Home, title: 'Home' },
  about: { component: About, title: 'About Us' },
  destination: { component: Destination, title: 'Destinations' },
  north: { component: Northern, title: 'Northern Province' },
  east: { component: Eastern, title: 'Eastern Province' },
  south: { component: Southern, title: 'Southern Province' },
  west: { component: Western, title: 'Western Province' },
  service: { component: Service, title: 'Services' },
  contact: { component: Contact, title: 'Contact Us' }
}
</script>
<template>
  <div :style="wrapperStyle" class="min-h-screen bg-emerald-50 text-slate-900 flex flex-col">
    <Navbar @navigate="(page) => currentPage = page" :current-page="currentPage" />
    <main class="max-w-7xl mx-auto px-4 py-12 flex-grow w-full">
      <component :is="pages[currentPage].component" @navigate="(page) => currentPage = page" />
    </main>
     <Footer @navigate="(page) => currentPage = page" :current-page="currentPage" />
     </div>
</template>