<template>
  <nav class="bg-slate-900 text-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <a href="/" class="text-2xl font-bold">TechCorp</a>
        </div>

        <!-- Navigation Links -->
        <div class="hidden md:flex items-center space-x-8">
          <a href="/" class="hover:text-blue-400 transition-colors">Home</a>

          <!-- Products Dropdown -->
          <div class="relative">
            <button 
              @click="isProductsOpen = !isProductsOpen"
              class="flex items-center space-x-1 hover:text-blue-400 transition-colors"
            >
              <span>Products</span>
              <ChevronDownIcon class="w-4 h-4" />
            </button>
            <div 
              v-if="isProductsOpen" 
              class="absolute top-full left-0 mt-2 w-48 bg-white text-gray-900 rounded-md shadow-lg py-2 z-50"
            >
              <a href="/products/web" class="block px-4 py-2 hover:bg-gray-100">Web Development</a>
              <a href="/products/mobile" class="block px-4 py-2 hover:bg-gray-100">Mobile Apps</a>
              <a href="/products/ai" class="block px-4 py-2 hover:bg-gray-100">AI Solutions</a>
            </div>
          </div>

          <!-- Resources Dropdown -->
          <div class="relative">
            <button 
              @click="isResourcesOpen = !isResourcesOpen"
              class="flex items-center space-x-1 hover:text-blue-400 transition-colors"
            >
              <span>Resources</span>
              <ChevronDownIcon class="w-4 h-4" />
            </button>
            <div 
              v-if="isResourcesOpen" 
              class="absolute top-full left-0 mt-2 w-48 bg-white text-gray-900 rounded-md shadow-lg py-2 z-50"
            >
              <a href="/blog" class="block px-4 py-2 hover:bg-gray-100">Blog</a>
              <a href="/docs" class="block px-4 py-2 hover:bg-gray-100">Documentation</a>
              <a href="/support" class="block px-4 py-2 hover:bg-gray-100">Support</a>
            </div>
          </div>

          <a href="/pricing" class="hover:text-blue-400 transition-colors">Pricing</a>
        </div>

        <!-- Auth Buttons -->
        <div class="hidden md:flex items-center space-x-4">
          <a href="/login" class="hover:text-blue-400 transition-colors">Sign In</a>
          <button class="bg-blue-600 text-white px-4 py-2 rounded-md hover:bg-blue-700 transition-colors">
            Sign Up
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import { ChevronDown as ChevronDownIcon } from 'lucide-vue-next'

const isProductsOpen = ref(false)
const isResourcesOpen = ref(false)
</script>

<style scoped>
.transition-colors {
  transition: color 0.2s ease-in-out;
}
</style>