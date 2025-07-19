<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-900 via-purple-900 to-pink-900">
    <!-- Liquid Wave Navbar -->
    <nav class="relative overflow-hidden">
      <!-- Animated background waves -->
      <div class="absolute inset-0">
        <svg class="absolute bottom-0 w-full h-full" viewBox="0 0 1200 120" preserveAspectRatio="none">
          <path 
            d="M0,0V46.29c47.79,22.2,103.59,32.17,158,28,70.36-5.37,136.33-33.31,206.8-37.5C438.64,32.43,512.34,53.67,583,72.05c69.27,18,138.3,24.88,209.4,13.08,36.15-6,69.85-17.84,104.45-29.34C989.49,25,1113-14.29,1200,52.47V0Z" 
            :fill="waveColor1"
            class="animate-wave-1"
          />
          <path 
            d="M0,0V15.81C13,36.92,27.64,56.86,47.69,72.05,99.41,111.27,165,111,224.58,91.58c31.15-10.15,60.09-26.07,89.67-39.8,40.92-19,84.73-46,130.83-49.67,36.26-2.85,70.9,9.42,98.6,31.56,31.77,25.39,62.32,62,103.63,73,40.44,10.79,81.35-6.69,119.13-24.28s75.16-39,116.92-43.05c59.73-5.85,113.28,22.88,168.9,38.84,30.2,8.66,59,6.17,87.09-7.5,22.43-10.89,48-26.93,60.65-49.24V0Z" 
            :fill="waveColor2"
            class="animate-wave-2"
          />
          <path 
            d="M0,0V5.63C149.93,59,314.09,71.32,475.83,42.57c43-7.64,84.23-20.12,127.61-26.46,59-8.63,112.48,12.24,165.56,35.4C827.93,77.22,886,95.24,951.2,90c86.53-7,172.46-45.71,248.8-84.81V0Z" 
            :fill="waveColor3"
            class="animate-wave-3"
          />
        </svg>
      </div>

      <!-- Navbar content -->
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-20">
          <!-- Logo with liquid effect -->
          <div class="flex items-center space-x-3">
            <div class="relative">
              <div class="w-10 h-10 bg-gradient-to-r from-cyan-400 to-blue-500 rounded-full animate-bounce"></div>
              <div class="absolute inset-0 w-10 h-10 bg-gradient-to-r from-blue-500 to-purple-500 rounded-full animate-ping opacity-20"></div>
            </div>
            <span class="text-2xl font-bold text-white">LiquidNav</span>
          </div>

          <!-- Navigation Links -->
          <div class="hidden md:flex items-center space-x-8">
            <a 
              v-for="(link, index) in navLinks" 
              :key="link.name"
              :href="link.href"
              @mouseenter="createRipple"
              class="relative text-white/90 hover:text-white transition-all duration-300 px-4 py-2 rounded-full overflow-hidden group"
            >
              <span class="relative z-10">{{ link.name }}</span>
              <!-- Liquid hover effect -->
              <div class="absolute inset-0 bg-gradient-to-r from-cyan-500/20 to-blue-500/20 rounded-full scale-0 group-hover:scale-100 transition-transform duration-500 ease-out"></div>
              <div class="absolute inset-0 bg-white/10 rounded-full scale-0 group-hover:scale-110 transition-transform duration-700 ease-out delay-100"></div>
            </a>
          </div>

          <!-- Animated CTA Button -->
          <button 
            @click="createSplash"
            class="relative overflow-hidden bg-gradient-to-r from-pink-500 to-violet-500 text-white px-8 py-3 rounded-full font-semibold transition-all duration-300 hover:scale-105 hover:shadow-2xl group"
          >
            <span class="relative z-10">Dive In</span>
            <!-- Liquid splash effect -->
            <div 
              v-for="splash in splashes" 
              :key="splash.id"
              class="absolute inset-0 bg-gradient-to-r from-violet-500 to-pink-500 rounded-full animate-splash"
              :style="{ animationDelay: splash.delay + 'ms' }"
            ></div>
          </button>
        </div>
      </div>
    </nav>

    <!-- Content -->
    <div class="relative z-10 pt-20 px-8 text-center text-white">
      <h1 class="text-6xl font-bold mb-6 animate-float">
        Liquid Waves
      </h1>
      <p class="text-xl text-white/80 mb-8 animate-float animation-delay-300">
        Flowing animations that mesmerize and engage
      </p>
      <div class="flex justify-center space-x-4">
        <div 
          v-for="i in 3" 
          :key="i"
          class="w-4 h-4 bg-white/60 rounded-full animate-bounce"
          :style="{ animationDelay: (i * 0.2) + 's' }"
        ></div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const splashes = ref([])
const splashId = ref(0)

const navLinks = [
  { name: 'Home', href: '/' },
  { name: 'About', href: '/about' },
  { name: 'Portfolio', href: '/portfolio' },
  { name: 'Contact', href: '/contact' }
]

const waveColor1 = computed(() => 'rgba(59, 130, 246, 0.3)')
const waveColor2 = computed(() => 'rgba(147, 51, 234, 0.2)')
const waveColor3 = computed(() => 'rgba(236, 72, 153, 0.1)')

const createRipple = (event) => {
  // Add ripple effect logic here
  console.log('Ripple effect triggered')
}

const createSplash = () => {
  const newSplash = {
    id: splashId.value++,
    delay: 0
  }
  splashes.value.push(newSplash)
  
  setTimeout(() => {
    splashes.value = splashes.value.filter(s => s.id !== newSplash.id)
  }, 1000)
}
</script>

<style scoped>
@keyframes wave-1 {
  0%, 100% { transform: translateX(0) translateY(0); }
  50% { transform: translateX(-25px) translateY(-10px); }
}

@keyframes wave-2 {
  0%, 100% { transform: translateX(0) translateY(0); }
  50% { transform: translateX(25px) translateY(-15px); }
}

@keyframes wave-3 {
  0%, 100% { transform: translateX(0) translateY(0); }
  50% { transform: translateX(-15px) translateY(-5px); }
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

@keyframes splash {
  0% { transform: scale(0); opacity: 1; }
  100% { transform: scale(2); opacity: 0; }
}

.animate-wave-1 { animation: wave-1 8s ease-in-out infinite; }
.animate-wave-2 { animation: wave-2 6s ease-in-out infinite reverse; }
.animate-wave-3 { animation: wave-3 10s ease-in-out infinite; }
.animate-float { animation: float 3s ease-in-out infinite; }
.animate-splash { animation: splash 0.8s ease-out forwards; }

.animation-delay-300 {
  animation-delay: 0.3s;
}
</style>