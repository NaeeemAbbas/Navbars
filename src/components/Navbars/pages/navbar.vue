<template>
  <div class="bg-white">
    <nav class="fixed top-8 left-1/2 transform -translate-x-1/2 z-50 w-[calc(100%-2rem)] max-w-5xl">
      <div class="bg-white/60 backdrop-blur-lg rounded-full px-4 py-3 border border-gray-200 shadow-lg">
        <div class="flex items-center justify-between">
          <div class="flex items-center cursor-pointer flex-shrink-0">
            <img src="/src/assets/logo.png" alt="" class="w-10 sm:w-14">
          </div>

          <div class="hidden md:flex items-center space-x-6">
            <a
              v-for="(link, index) in navLinks"
              :key="link.name"
              :href="link.href"
              @mouseenter="hoveredIndex = index"
              @mouseleave="hoveredIndex = null"
              class="relative text-gray-800 transition-all duration-300 px-4 py-2 rounded-full hover:bg-gray-100 text-lg font-medium"
            >
              {{ link.name }}
            </a>
          </div>

          <button class="relative overflow-hidden bg-[#9552E3] text-white px-6 py-3 cursor-pointer rounded-full font-medium transition-all duration-300 hover:scale-105 transform shadow-md hover:shadow-lg focus:outline-none focus:ring-2 focus:ring-purple-500 focus:ring-opacity-50 flex-shrink-0 hidden md:block">
            <span class="relative z-10">Get Started</span>
            <div class="absolute inset-0 bg-gradient-to-r from-violet-500 to-pink-500 opacity-0 hover:opacity-100 transition-opacity duration-300"></div>
          </button>

          <button
            @click="isMobileOpen = !isMobileOpen"
            class="md:hidden text-gray-700 p-2 rounded-full hover:bg-gray-100 transition-colors"
            aria-label="Toggle navigation menu"
          >
            <MenuIcon v-if="!isMobileOpen" class="w-6 h-6" />
            <XIcon v-else class="w-6 h-6" />
          </button>
        </div>
      </div>

      <transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="transform -translate-y-4 opacity-0"
        enter-to-class="transform translate-y-0 opacity-100"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="transform translate-y-0 opacity-100"
        leave-to-class="transform -translate-y-4 opacity-0"
      >
        <div v-if="isMobileOpen" class="mt-4 bg-white/60 backdrop-blur-lg rounded-2xl border border-gray-200 p-4 md:hidden shadow-lg">
          <div class="space-y-2">
            <a
              v-for="link in navLinks"
              :key="link.name"
              :href="link.href"
              @click="isMobileOpen = false"
              class="block text-gray-800 hover:bg-gray-100 px-4 py-3 rounded-xl transition-all duration-200 font-medium"
            >
              {{ link.name }}
            </a>
            <button
              class="relative overflow-hidden bg-[#9552E3] text-white w-full py-3 mt-4 cursor-pointer rounded-full font-medium transition-all duration-300 hover:scale-[1.02] transform shadow-md hover:shadow-lg focus:outline-none focus:ring-2 focus:ring-purple-500 focus:ring-opacity-50"
              @click="isMobileOpen = false; /* Add actual action for join waitlist here */"
            >
              <span class="relative z-10">Get Started</span>
              <div class="absolute inset-0 bg-gradient-to-r from-violet-500 to-pink-500 opacity-0 hover:opacity-100 transition-opacity duration-300"></div>
            </button>
          </div>
        </div>
      </transition>
    </nav>

    
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { Menu as MenuIcon, X as XIcon } from 'lucide-vue-next';

const hoveredIndex = ref(null);
const isMobileOpen = ref(false);

const navLinks = [
  { name: 'Benefits', href: '#benefits' },
  { name: 'Pricing', href: '#pricing' },
  { name: 'Testimonials', href: '#testimonials' },
];
</script>

<style scoped>
/* No specific custom CSS needed beyond Tailwind utility classes for this component. */
</style>