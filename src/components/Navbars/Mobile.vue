<template>
  <nav class="bg-gradient-to-r from-purple-600 to-blue-600 text-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <a href="/" class="text-2xl font-bold">MobileFirst</a>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <a href="/" class="hover:text-purple-200 transition-colors">Home</a>
          <a href="/features" class="hover:text-purple-200 transition-colors">Features</a>
          <a href="/pricing" class="hover:text-purple-200 transition-colors">Pricing</a>
          <a href="/about" class="hover:text-purple-200 transition-colors">About</a>
          <button class="bg-white text-purple-600 px-4 py-2 rounded-md font-medium hover:bg-purple-50 transition-colors">
            Get Started
          </button>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden">
          <button 
            @click="isOpen = !isOpen" 
            class="p-2 rounded-md hover:bg-purple-700 transition-colors"
          >
            <XIcon v-if="isOpen" class="w-6 h-6" />
            <MenuIcon v-else class="w-6 h-6" />
          </button>
        </div>
      </div>

      <!-- Mobile Navigation -->
      <transition
        enter-active-class="transition duration-200 ease-out"
        enter-from-class="transform scale-95 opacity-0"
        enter-to-class="transform scale-100 opacity-100"
        leave-active-class="transition duration-75 ease-in"
        leave-from-class="transform scale-100 opacity-100"
        leave-to-class="transform scale-95 opacity-0"
      >
        <div v-if="isOpen" class="md:hidden">
          <div class="px-2 pt-2 pb-3 space-y-1 bg-purple-700 rounded-md mt-2">
            <a
              href="/"
              @click="isOpen = false"
              class="block px-3 py-2 rounded-md hover:bg-purple-600 transition-colors"
            >
              Home
            </a>
            <a
              href="/features"
              @click="isOpen = false"
              class="block px-3 py-2 rounded-md hover:bg-purple-600 transition-colors"
            >
              Features
            </a>
            <a
              href="/pricing"
              @click="isOpen = false"
              class="block px-3 py-2 rounded-md hover:bg-purple-600 transition-colors"
            >
              Pricing
            </a>
            <a
              href="/about"
              @click="isOpen = false"
              class="block px-3 py-2 rounded-md hover:bg-purple-600 transition-colors"
            >
              About
            </a>
            <button class="w-full text-left bg-white text-purple-600 px-3 py-2 rounded-md font-medium hover:bg-purple-50 transition-colors">
              Get Started
            </button>
          </div>
        </div>
      </transition>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import { Menu as MenuIcon, X as XIcon } from 'lucide-vue-next'

const isOpen = ref(false)
</script>

<style scoped>
.transition-colors {
  transition: color 0.2s ease-in-out;
}
</style>