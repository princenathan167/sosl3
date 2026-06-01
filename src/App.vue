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
import Photos from './component/photos.vue'
import Videos from './component/videos.vue'
import bg from './assets/bg.jpg'

const currentPage = ref('home')

const wrapperStyle = computed(() => currentPage.value === 'home'
  ? { backgroundImage: `url(${bg})`, backgroundSize: 'contain', backgroundPosition: 'center', backgroundRepeat: 'no-repeat' }
  : {})

const pages = {
  home: { component: Home },
  about: { component: About },
  destination: { component: Destination },
  kigali: { component: Home }, 
  northern: { component: Northern },
  eastern: { component: Eastern },
  southern: { component: Southern },
  western: { component: Western },
  service: { component: Service },
  photos: { component: Photos },
  videos: { component: Videos }, // Synced with the new Videos.vue
  contact: { component: Contact }
}
</script>

<template>
  <div :style="wrapperStyle" class="min-h-screen bg-emerald-50 text-slate-900 flex flex-col">
    <Navbar @navigate="(page) => currentPage = page" :current-page="currentPage" />
    <main class="max-w-7xl mx-auto px-4 py-12 flex-grow w-full">
      <component v-if="pages[currentPage]" :is="pages[currentPage].component" @navigate="(page) => currentPage = page" />
    </main>
    <Footer @navigate="(page) => currentPage = page" :current-page="currentPage" />
  </div>
</template>
