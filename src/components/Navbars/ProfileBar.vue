<template>
  <nav class="bg-white shadow-sm border-b">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <a href="/" class="text-2xl font-bold text-indigo-600">ProApp</a>
        </div>

        <!-- Navigation Links -->
        <div class="hidden md:flex items-center space-x-8">
          <a href="/dashboard" class="text-gray-900 hover:text-indigo-600 transition-colors">Dashboard</a>
          <a href="/projects" class="text-gray-500 hover:text-gray-900 transition-colors">Projects</a>
          <a href="/team" class="text-gray-500 hover:text-gray-900 transition-colors">Team</a>
          <a href="/analytics" class="text-gray-500 hover:text-gray-900 transition-colors">Analytics</a>
        </div>

        <!-- Right Side Actions -->
        <div class="flex items-center space-x-4">
          <!-- Notifications -->
          <div class="relative">
            <button 
              @click="isNotificationsOpen = !isNotificationsOpen"
              class="p-2 text-gray-400 hover:text-gray-600 transition-colors relative"
            >
              <BellIcon class="w-6 h-6" />
              <span class="absolute -top-1 -right-1 bg-red-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">
                {{ notifications.length }}
              </span>
            </button>
            <transition
              enter-active-class="transition duration-200 ease-out"
              enter-from-class="transform scale-95 opacity-0"
              enter-to-class="transform scale-100 opacity-100"
              leave-active-class="transition duration-75 ease-in"
              leave-from-class="transform scale-100 opacity-100"
              leave-to-class="transform scale-95 opacity-0"
            >
              <div 
                v-if="isNotificationsOpen" 
                class="absolute right-0 top-full mt-2 w-80 bg-white rounded-md shadow-lg border py-2 z-50"
              >
                <div class="px-4 py-2 border-b">
                  <h3 class="font-semibold text-gray-900">Notifications</h3>
                </div>
                <div class="max-h-64 overflow-y-auto">
                  <div 
                    v-for="notification in notifications" 
                    :key="notification.id"
                    class="px-4 py-3 hover:bg-gray-50 border-b last:border-b-0"
                  >
                    <div class="flex items-start space-x-3">
                      <component :is="notification.icon" :class="notification.iconColor" class="w-5 h-5 mt-0.5" />
                      <div>
                        <p class="text-sm font-medium text-gray-900">{{ notification.message }}</p>
                        <p class="text-xs text-gray-500">{{ notification.time }}</p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </transition>
          </div>

          <!-- Profile Dropdown -->
          <div class="relative">
            <button 
              @click="isProfileOpen = !isProfileOpen"
              class="flex items-center space-x-3 p-2 rounded-md hover:bg-gray-100 transition-colors"
            >
              <div class="w-8 h-8 bg-indigo-600 rounded-full flex items-center justify-center">
                <span class="text-sm font-medium text-white">{{ user.initials }}</span>
              </div>
              <div class="hidden md:block text-left">
                <p class="text-sm font-medium text-gray-900">{{ user.name }}</p>
                <p class="text-xs text-gray-500">{{ user.email }}</p>
              </div>
              <ChevronDownIcon class="w-4 h-4 text-gray-400" />
            </button>
            <transition
              enter-active-class="transition duration-200 ease-out"
              enter-from-class="transform scale-95 opacity-0"
              enter-to-class="transform scale-100 opacity-100"
              leave-active-class="transition duration-75 ease-in"
              leave-from-class="transform scale-100 opacity-100"
              leave-to-class="transform scale-95 opacity-0"
            >
              <div 
                v-if="isProfileOpen" 
                class="absolute right-0 top-full mt-2 w-48 bg-white rounded-md shadow-lg border py-2 z-50"
              >
                <a href="/profile" class="flex items-center px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
                  <UserIcon class="w-4 h-4 mr-3" />
                  Your Profile
                </a>
                <a href="/settings" class="flex items-center px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
                  <SettingsIcon class="w-4 h-4 mr-3" />
                  Settings
                </a>
                <hr class="my-2" />
                <button 
                  @click="handleLogout"
                  class="flex items-center w-full px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                >
                  <LogOutIcon class="w-4 h-4 mr-3" />
                  Sign out
                </button>
              </div>
            </transition>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import { 
  Bell as BellIcon, 
  ChevronDown as ChevronDownIcon, 
  User as UserIcon, 
  Settings as SettingsIcon, 
  LogOut as LogOutIcon,
  Mail as MailIcon,
  Users as UsersIcon
} from 'lucide-vue-next'

const isProfileOpen = ref(false)
const isNotificationsOpen = ref(false)

const user = ref({
  name: 'Alex Smith',
  email: 'alex@example.com',
  initials: 'AS'
})

const notifications = ref([
  {
    id: 1,
    message: 'New message received',
    time: '2 minutes ago',
    icon: MailIcon,
    iconColor: 'text-blue-500'
  },
  {
    id: 2,
    message: 'New team member joined',
    time: '1 hour ago',
    icon: UsersIcon,
    iconColor: 'text-green-500'
  }
])

const handleLogout = () => {
  console.log('Logging out...')
  // Implement logout functionality here
  isProfileOpen.value = false
}
</script>

<style scoped>
.transition-colors {
  transition: color 0.2s ease-in-out;
}
</style>