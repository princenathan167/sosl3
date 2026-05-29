<script setup>
defineProps({
  currentPage: String
})

const emit = defineEmits(['navigate'])

const navigate = (page) => {
  emit('navigate', page)
}
</script>

<template>
  <footer class="bg-gradient-to-r from-green-600 to-green-700 text-white">
    <!-- Main Footer Content -->
    <div class="max-w-7xl mx-auto px-4 py-16">
      <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
        <!-- About Section -->
        <div class="footer-section">
          <h3 class="text-xl font-bold mb-4">TEMBERA U RWANDA</h3>
          <p class="text-green-50 text-sm leading-relaxed">
            Discover the beauty and wonder of Rwanda. Explore our lush landscapes, vibrant culture, and unforgettable experiences across the country's stunning regions.
          </p>
        </div>

        <!-- Quick Links -->
        <div class="footer-section">
          <h3 class="text-lg font-bold mb-4 border-b-2 border-green-300 pb-2">Quick Links</h3>
          <ul class="space-y-2">
            <li><button @click="navigate('home')" class="text-green-50 hover:text-white transition bg-none border-none cursor-pointer">Home</button></li>
            <li><button @click="navigate('about')" class="text-green-50 hover:text-white transition bg-none border-none cursor-pointer">About Us</button></li>
            <li><button @click="navigate('service')" class="text-green-50 hover:text-white transition bg-none border-none cursor-pointer">Services</button></li>
            <li><button @click="navigate('contact')" class="text-green-50 hover:text-white transition bg-none border-none cursor-pointer">Contact</button></li>
          </ul>
        </div>

        <!-- Cardinal Provinces -->
        <div class="footer-section">
          <h3 class="text-lg font-bold mb-4 border-b-2 border-green-300 pb-2">Explore Provinces</h3>
          <ul class="space-y-2">
            <li><button @click="navigate('north')" class="text-green-50 hover:text-white transition bg-none border-none cursor-pointer">Northern Region</button></li>
            <li><button @click="navigate('south')" class="text-green-50 hover:text-white transition bg-none border-none cursor-pointer">Southern Region</button></li>
            <li><button @click="navigate('east')" class="text-green-50 hover:text-white transition bg-none border-none cursor-pointer">Eastern Region</button></li>
            <li><button @click="navigate('west')" class="text-green-50 hover:text-white transition bg-none border-none cursor-pointer">Western Region</button></li>
          </ul>
        </div>

        <!-- Contact Information -->
        <div class="footer-section">
          <h3 class="text-lg font-bold mb-4 border-b-2 border-green-300 pb-2">Contact Us</h3>
          <ul class="space-y-3 text-green-50 text-sm">
            <li class="flex items-start">
              <span class="mr-2"></span>
              <a href="mailto:info@temberarwanda.com" class="hover:text-white transition">info@temberarwanda.com</a>
            </li>
            <li class="flex items-start">
              <span class="mr-2"></span>
              <a href="tel:+250788123456" class="hover:text-white transition">+250 788 123 456</a>
            </li>
            <li class="flex items-start">
              <span class="mr-2"></span>
              <span>Kigali, Rwanda</span>
            </li>
            <li class="flex items-start">
              <span class="mr-2"></span>
              <span>P.O. Box 1234</span>
            </li>
          </ul>
        </div>
      </div>

      <!-- Divider -->
      <div class="border-t border-green-400 my-8"></div>

      <!-- Footer Bottom -->
      <div class="flex flex-col md:flex-row justify-between items-center">
        <p class="text-green-50 text-sm">
          © 2026 TEMBERA U RWANDA. All rights reserved.
        </p>
        <p class="text-green-50 text-xs mt-4 md:mt-0">
          Experience Rwanda • Explore Nature • Create Memories
        </p>
      </div>
    </div>
  </footer>
</template>

