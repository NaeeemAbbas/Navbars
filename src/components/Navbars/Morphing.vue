<template>
  <div class="flex min-h-screen bg-gray-100">
    <!-- Morphing Sidebar -->
    <div 
      class="fixed left-0 top-0 h-full bg-gradient-to-b from-indigo-900 to-purple-900 text-white transition-all duration-500 ease-in-out z-50"
      :class="isExpanded ? 'w-64' : 'w-16'"
    >
      <!-- Toggle Button -->
      <button 
        @click="isExpanded = !isExpanded"
        class="absolute -right-3 top-6 w-6 h-6 bg-white text-indigo-900 rounded-full flex items-center justify-center shadow-lg hover:scale-110 transition-transform duration-200"
      >
        <ChevronRightIcon 
          class="w-4 h-4 transition-transform duration-300"
          :class="isExpanded ? 'rotate-180' : ''"
        />
      </button>

      <!-- Logo -->
      <div class="p-4 border-b border-white/20">
        <div class="flex items-center space-x-3">
          <div class="w-8 h-8 bg-gradient-to-r from-pink-500 to-yellow-500 rounded-lg flex items-center justify-center">
            <SparklesIcon class="w-5 h-5 text-white" />
          </div>
          <transition
            enter-active-class="transition duration-300 ease-out"
            enter-from-class="opacity-0 transform translate-x-4"
            enter-to-class="opacity-100 transform translate-x-0"
            leave-active-class="transition duration-200 ease-in"
            leave-from-class="opacity-100 transform translate-x-0"
            leave-to-class="opacity-0 transform translate-x-4"
          >
            <span v-if="isExpanded" class="font-bold text-lg">MorphNav</span>
          </transition>
        </div>
      </div>

      <!-- Navigation -->
      <nav class="mt-8">
        <div class="space-y-2 px-3">
          <div 
            v-for="(item, index) in navigation" 
            :key="item.name"
            @click="activeIndex = index"
            class="relative group cursor-pointer"
          >
            <div 
              class="flex items-center p-3 rounded-xl transition-all duration-300 hover:bg-white/10"
              :class="activeIndex === index ? 'bg-white/20 shadow-lg' : ''"
            >
              <component 
                :is="item.icon" 
                class="w-6 h-6 transition-all duration-300"
                :class="activeIndex === index ? 'text-yellow-400 scale-110' : 'text-white/80'"
              />
              <transition
                enter-active-class="transition duration-300 ease-out"
                enter-from-class="opacity-0 transform translate-x-4"
                enter-to-class="opacity-100 transform translate-x-0"
                leave-active-class="transition duration-200 ease-in"
                leave-from-class="opacity-100 transform translate-x-0"
                leave-to-class="opacity-0 transform translate-x-4"
              >
                <span 
                  v-if="isExpanded" 
                  class="ml-3 font-medium transition-colors duration-300"
                  :class="activeIndex === index ? 'text-white' : 'text-white/80'"
                >
                  {{ item.name }}
                </span>
              </transition>
            </div>

            <!-- Active indicator -->
            <div 
              class="absolute right-0 top-1/2 transform -translate-y-1/2 w-1 bg-yellow-400 rounded-l-full transition-all duration-300"
              :class="activeIndex === index ? 'h-8 opacity-100' : 'h-0 opacity-0'"
            ></div>

            <!-- Tooltip for collapsed state -->
            <div 
              v-if="!isExpanded"
              class="absolute left-full ml-2 top-1/2 transform -translate-y-1/2 bg-gray-900 text-white px-2 py-1 rounded text-sm opacity-0 group-hover:opacity-100 transition-opacity duration-200 pointer-events-none whitespace-nowrap z-10"
            >
              {{ item.name }}
            </div>
          </div>
        </div>
      </nav>

      <!-- User Profile -->
      <div class="absolute bottom-4 left-0 right-0 px-3">
        <div class="flex items-center p-3 bg-white/10 rounded-xl">
          <div class="w-8 h-8 bg-gradient-to-r from-green-400 to-blue-500 rounded-full flex items-center justify-center">
            <span class="text-xs font-bold">JD</span>
          </div>
          <transition
            enter-active-class="transition duration-300 ease-out"
            enter-from-class="opacity-0 transform translate-x-4"
            enter-to-class="opacity-100 transform translate-x-0"
            leave-active-class="transition duration-200 ease-in"
            leave-from-class="opacity-100 transform translate-x-0"
            leave-to-class="opacity-0 transform translate-x-4"
          >
            <div v-if="isExpanded" class="ml-3">
              <p class="text-sm font-medium">John Doe</p>
              <p class="text-xs text-white/60">Administrator</p>
            </div>
          </transition>
        </div>
      </div>
    </div>

    <!-- Main Content -->
    <div 
      class="flex-1 transition-all duration-500 ease-in-out"
      :class="isExpanded ? 'ml-64' : 'ml-16'"
    >
      <div class="p-8">
        <h1 class="text-3xl font-bold text-gray-900 mb-4">Morphing Sidebar</h1>
        <p class="text-gray-600 mb-8">Click the arrow to expand/collapse the sidebar with smooth animations.</p>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div 
            v-for="i in 6" 
            :key="i"
            class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300"
          >
            <h3 class="text-lg font-semibold mb-2">Card {{ i }}</h3>
            <p class="text-gray-600">This is a sample card to demonstrate the layout.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { 
  ChevronRight as ChevronRightIcon,
  Sparkles as SparklesIcon,
  Home,
  Users,
  BarChart3,
  Settings,
  FileText,
  HelpCircle
} from 'lucide-vue-next'

const isExpanded = ref(true)
const activeIndex = ref(0)

const navigation = [
  { name: 'Dashboard', icon: Home },
  { name: 'Users', icon: Users },
  { name: 'Analytics', icon: BarChart3 },
  { name: 'Reports', icon: FileText },
  { name: 'Settings', icon: Settings },
  { name: 'Help', icon: HelpCircle }
]
</script>