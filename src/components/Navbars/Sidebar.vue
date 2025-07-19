<template>
  <div class="flex">
    <!-- Sidebar -->
    <div class="fixed inset-y-0 left-0 w-64 bg-gray-900 text-white">
      <!-- Logo -->
      <div class="flex items-center justify-center h-16 bg-gray-800">
        <h1 class="text-xl font-bold">Dashboard</h1>
      </div>

      <!-- Navigation -->
      <nav class="mt-8">
        <div class="px-4 space-y-2">
          <a
            v-for="item in navigation"
            :key="item.name"
            :href="item.href"
            :class="[
              'flex items-center px-4 py-3 text-sm font-medium rounded-lg transition-colors',
              item.current ? 'bg-blue-600 text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white'
            ]"
          >
            <component :is="item.icon" class="w-5 h-5 mr-3" />
            {{ item.name }}
          </a>
        </div>
      </nav>

      <!-- User Profile -->
      <div class="absolute bottom-0 w-full p-4 bg-gray-800">
        <div class="flex items-center">
          <div class="w-10 h-10 bg-blue-600 rounded-full flex items-center justify-center">
            <span class="text-sm font-medium">JD</span>
          </div>
          <div class="ml-3">
            <p class="text-sm font-medium">John Doe</p>
            <p class="text-xs text-gray-400">john@example.com</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Main Content Area -->
    <div class="ml-64 flex-1 p-8">
      <h2 class="text-2xl font-bold mb-4">Sidebar Navigation</h2>
      <p class="text-gray-600">This is the main content area. The sidebar is fixed on the left.</p>
      <div class="mt-8 p-6 bg-white rounded-lg shadow">
        <h3 class="text-lg font-semibold mb-2">Content Example</h3>
        <p class="text-gray-600">Your main application content would go here.</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { Home, Users, Settings, BarChart3, FileText, HelpCircle } from 'lucide-vue-next'

const navigation = [
  { name: "Dashboard", href: "/", icon: Home, current: true },
  { name: "Users", href: "/users", icon: Users, current: false },
  { name: "Analytics", href: "/analytics", icon: BarChart3, current: false },
  { name: "Reports", href: "/reports", icon: FileText, current: false },
  { name: "Settings", href: "/settings", icon: Settings, current: false },
  { name: "Help", href: "/help", icon: HelpCircle, current: false },
]
</script>

<style scoped>
.transition-colors {
  transition: color 0.2s ease-in-out;
}
</style>