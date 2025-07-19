<template>
  <nav class="bg-white shadow-md border-b">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <a href="/" class="text-2xl font-bold text-orange-600">ShopHub</a>
        </div>

        <!-- Search Bar -->
        <div class="flex-1 max-w-2xl mx-8">
          <div class="relative">
            <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
              <SearchIcon class="h-5 w-5 text-gray-400" />
            </div>
            <input
              v-model="searchQuery"
              type="text"
              placeholder="Search products, brands, and more..."
              class="block w-full pl-10 pr-3 py-2 border border-gray-300 rounded-lg leading-5 bg-white placeholder-gray-500 focus:outline-none focus:placeholder-gray-400 focus:ring-2 focus:ring-orange-500 focus:border-orange-500"
              @keyup.enter="handleSearch"
            />
          </div>
        </div>

        <!-- Navigation Links -->
        <div class="hidden md:flex items-center space-x-6">
          <a href="/categories" class="text-gray-700 hover:text-orange-600 transition-colors">Categories</a>
          <a href="/deals" class="text-gray-700 hover:text-orange-600 transition-colors">Deals</a>
          <a href="/brands" class="text-gray-700 hover:text-orange-600 transition-colors">Brands</a>
        </div>

        <!-- Action Icons -->
        <div class="flex items-center space-x-4">
          <button class="p-2 text-gray-400 hover:text-gray-600 transition-colors relative">
            <BellIcon class="w-6 h-6" />
            <span class="absolute -top-1 -right-1 bg-red-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">
              2
            </span>
          </button>
          <button class="p-2 text-gray-400 hover:text-gray-600 transition-colors relative">
            <ShoppingCartIcon class="w-6 h-6" />
            <span class="absolute -top-1 -right-1 bg-orange-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">
              {{ cartCount }}
            </span>
          </button>
          <button class="bg-orange-600 text-white px-4 py-2 rounded-md hover:bg-orange-700 transition-colors">
            Sign In
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import { Search as SearchIcon, Bell as BellIcon, ShoppingCart as ShoppingCartIcon } from 'lucide-vue-next'

const searchQuery = ref('')
const cartCount = ref(3)

const handleSearch = () => {
  if (searchQuery.value.trim()) {
    console.log('Searching for:', searchQuery.value)
    // Implement search functionality here
  }
}
</script>

<style scoped>
.transition-colors {
  transition: color 0.2s ease-in-out;
}
</style>