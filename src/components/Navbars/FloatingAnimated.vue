<template>
  <div class="min-h-screen bg-gradient-to-br from-purple-900 via-blue-900 to-indigo-900">
    <!-- Floating Navbar -->
    <nav class="fixed top-6 left-1/2 transform -translate-x-1/2 z-50">
      <div class="bg-white/10 backdrop-blur-lg rounded-full px-8 py-4 border border-white/20 shadow-2xl">
        <div class="flex items-center space-x-8">
          <!-- Logo with pulse animation -->
          <div class="flex items-center space-x-2">
            <div class="w-8 h-8 bg-gradient-to-r from-pink-500 to-violet-500 rounded-full animate-pulse"></div>
            <span class="text-white font-bold text-lg">FloatNav</span>
          </div>

          <!-- Navigation Links with hover animations -->
          <div class="hidden md:flex items-center space-x-6">
            <a 
              v-for="(link, index) in navLinks" 
              :key="link.name"
              :href="link.href"
              @mouseenter="hoveredIndex = index"
              @mouseleave="hoveredIndex = null"
              class="relative text-white/80 hover:text-white transition-all duration-300 px-4 py-2 rounded-full"
              :class="{ 'text-white bg-white/20': hoveredIndex === index }"
            >
              {{ link.name }}
              <!-- Animated underline -->
              <div 
                class="absolute bottom-0 left-0 h-0.5 bg-gradient-to-r from-pink-500 to-violet-500 transition-all duration-300"
                :class="hoveredIndex === index ? 'w-full' : 'w-0'"
              ></div>
            </a>
          </div>

          <!-- CTA Button with gradient animation -->
          <button class="relative overflow-hidden bg-gradient-to-r from-pink-500 to-violet-500 text-white px-6 py-2 rounded-full font-medium transition-all duration-300 hover:scale-105 hover:shadow-lg">
            <span class="relative z-10">Get Started</span>
            <div class="absolute inset-0 bg-gradient-to-r from-violet-500 to-pink-500 opacity-0 hover:opacity-100 transition-opacity duration-300"></div>
          </button>

          <!-- Mobile menu button -->
          <button 
            @click="isMobileOpen = !isMobileOpen"
            class="md:hidden text-white p-2 rounded-full hover:bg-white/20 transition-colors"
          >
            <MenuIcon v-if="!isMobileOpen" class="w-6 h-6" />
            <XIcon v-else class="w-6 h-6" />
          </button>
        </div>
      </div>

      <!-- Mobile Menu with slide animation -->
      <transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="transform -translate-y-4 opacity-0"
        enter-to-class="transform translate-y-0 opacity-100"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="transform translate-y-0 opacity-100"
        leave-to-class="transform -translate-y-4 opacity-0"
      >
        <div v-if="isMobileOpen" class="mt-4 bg-white/10 backdrop-blur-lg rounded-2xl border border-white/20 p-4 md:hidden">
          <div class="space-y-2">
            <a 
              v-for="link in navLinks" 
              :key="link.name"
              :href="link.href"
              @click="isMobileOpen = false"
              class="block text-white/80 hover:text-white hover:bg-white/20 px-4 py-3 rounded-xl transition-all duration-200"
            >
              {{ link.name }}
            </a>
          </div>
        </div>
      </transition>
    </nav>

    <!-- Content -->
    <div class="pt-32 px-8 text-center text-white">
      <h1 class="text-6xl font-bold mb-6 animate-fade-in-up">
        Floating Navigation
      </h1>
      <p class="text-xl text-white/80 animate-fade-in-up animation-delay-200">
        Beautiful floating navbar with smooth animations
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Menu as MenuIcon, X as XIcon } from 'lucide-vue-next'

const hoveredIndex = ref(null)
const isMobileOpen = ref(false)

const navLinks = [
  { name: 'Home', href: '/' },
  { name: 'About', href: '/about' },
  { name: 'Services', href: '/services' },
  { name: 'Contact', href: '/contact' }
]
</script>

<style scoped>
@keyframes fade-in-up {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-up {
  animation: fade-in-up 0.8s ease-out forwards;
}

.animation-delay-200 {
  animation-delay: 0.2s;
  opacity: 0;
}
</style>