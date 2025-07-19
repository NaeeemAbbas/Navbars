<template>
  <div class="min-h-screen bg-black relative overflow-hidden">
    <!-- Particle Background -->
    <div class="absolute inset-0">
      <div 
        v-for="particle in particles" 
        :key="particle.id"
        class="absolute w-1 h-1 bg-white rounded-full animate-float-particle"
        :style="{
          left: particle.x + '%',
          top: particle.y + '%',
          animationDelay: particle.delay + 's',
          animationDuration: particle.duration + 's',
          opacity: particle.opacity
        }"
      ></div>
    </div>

    <!-- Navbar -->
    <nav class="relative z-10 border-b border-white/10">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <!-- Logo with glow effect -->
          <div class="flex items-center space-x-3">
            <div class="relative">
              <div class="w-8 h-8 bg-gradient-to-r from-blue-400 to-purple-500 rounded-full animate-pulse-glow"></div>
              <div class="absolute inset-0 w-8 h-8 bg-gradient-to-r from-blue-400 to-purple-500 rounded-full blur-sm opacity-50 animate-pulse"></div>
            </div>
            <span class="text-white font-bold text-xl tracking-wider">PARTICLE</span>
          </div>

          <!-- Navigation Links with particle trail -->
          <div class="hidden md:flex items-center space-x-8">
            <a 
              v-for="(link, index) in navLinks" 
              :key="link.name"
              :href="link.href"
              @mouseenter="createTrail(index)"
              @mouseleave="clearTrail(index)"
              class="relative text-white/80 hover:text-white transition-all duration-300 px-4 py-2 group"
            >
              <span class="relative z-10 font-medium">{{ link.name }}</span>
              <!-- Particle trail -->
              <div 
                v-if="activeTrails[index]"
                class="absolute inset-0 pointer-events-none"
              >
                <div 
                  v-for="trail in activeTrails[index]" 
                  :key="trail.id"
                  class="absolute w-1 h-1 bg-blue-400 rounded-full animate-trail-particle"
                  :style="{
                    left: trail.x + 'px',
                    top: trail.y + 'px',
                    animationDelay: trail.delay + 's'
                  }"
                ></div>
              </div>
              <!-- Glow effect -->
              <div class="absolute inset-0 bg-gradient-to-r from-blue-500/20 to-purple-500/20 rounded-lg scale-0 group-hover:scale-100 transition-transform duration-300 blur-sm"></div>
            </a>
          </div>

          <!-- Glowing CTA Button -->
          <button 
            @click="explodeParticles"
            class="relative overflow-hidden bg-gradient-to-r from-blue-500 to-purple-600 text-white px-6 py-2 rounded-full font-semibold transition-all duration-300 hover:scale-105 group"
          >
            <span class="relative z-10">Launch</span>
            <!-- Button glow -->
            <div class="absolute inset-0 bg-gradient-to-r from-blue-400 to-purple-500 rounded-full blur-md opacity-50 group-hover:opacity-75 transition-opacity duration-300"></div>
            <!-- Explosion particles -->
            <div 
              v-for="explosion in explosions" 
              :key="explosion.id"
              class="absolute inset-0 pointer-events-none"
            >
              <div 
                v-for="particle in explosion.particles" 
                :key="particle.id"
                class="absolute w-1 h-1 bg-white rounded-full animate-explode"
                :style="{
                  left: '50%',
                  top: '50%',
                  transform: `translate(-50%, -50%) rotate(${particle.angle}deg) translateX(${particle.distance}px)`,
                  animationDelay: particle.delay + 's'
                }"
              ></div>
            </div>
          </button>

          <!-- Mobile menu -->
          <button 
            @click="isMobileOpen = !isMobileOpen"
            class="md:hidden text-white p-2 rounded-lg hover:bg-white/10 transition-colors"
          >
            <MenuIcon v-if="!isMobileOpen" class="w-6 h-6" />
            <XIcon v-else class="w-6 h-6" />
          </button>
        </div>
      </div>

      <!-- Mobile Menu -->
      <transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="transform -translate-y-full opacity-0"
        enter-to-class="transform translate-y-0 opacity-100"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="transform translate-y-0 opacity-100"
        leave-to-class="transform -translate-y-full opacity-0"
      >
        <div v-if="isMobileOpen" class="md:hidden bg-black/90 backdrop-blur-lg border-t border-white/10">
          <div class="px-4 py-4 space-y-2">
            <a 
              v-for="link in navLinks" 
              :key="link.name"
              :href="link.href"
              @click="isMobileOpen = false"
              class="block text-white/80 hover:text-white hover:bg-white/10 px-4 py-3 rounded-lg transition-all duration-200"
            >
              {{ link.name }}
            </a>
          </div>
        </div>
      </transition>
    </nav>

    <!-- Content -->
    <div class="relative z-10 pt-32 px-8 text-center text-white">
      <h1 class="text-7xl font-bold mb-6 bg-gradient-to-r from-blue-400 via-purple-500 to-pink-500 bg-clip-text text-transparent animate-pulse-text">
        PARTICLE MAGIC
      </h1>
      <p class="text-xl text-white/70 mb-8 animate-fade-in-up">
        Interactive particles that respond to your every move
      </p>
      <div class="flex justify-center items-center space-x-8">
        <div class="w-2 h-2 bg-blue-400 rounded-full animate-ping"></div>
        <div class="w-3 h-3 bg-purple-500 rounded-full animate-bounce"></div>
        <div class="w-2 h-2 bg-pink-400 rounded-full animate-ping animation-delay-500"></div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { Menu as MenuIcon, X as XIcon } from 'lucide-vue-next'

const particles = ref([])
const activeTrails = ref({})
const explosions = ref([])
const isMobileOpen = ref(false)
let particleId = 0
let explosionId = 0

const navLinks = [
  { name: 'Home', href: '/' },
  { name: 'About', href: '/about' },
  { name: 'Work', href: '/work' },
  { name: 'Contact', href: '/contact' }
]

const createParticles = () => {
  for (let i = 0; i < 50; i++) {
    particles.value.push({
      id: particleId++,
      x: Math.random() * 100,
      y: Math.random() * 100,
      delay: Math.random() * 5,
      duration: 3 + Math.random() * 4,
      opacity: 0.1 + Math.random() * 0.5
    })
  }
}

const createTrail = (index) => {
  activeTrails.value[index] = []
  for (let i = 0; i < 10; i++) {
    activeTrails.value[index].push({
      id: particleId++,
      x: Math.random() * 100,
      y: Math.random() * 20,
      delay: i * 0.1
    })
  }
}

const clearTrail = (index) => {
  setTimeout(() => {
    delete activeTrails.value[index]
  }, 1000)
}

const explodeParticles = () => {
  const explosion = {
    id: explosionId++,
    particles: []
  }
  
  for (let i = 0; i < 20; i++) {
    explosion.particles.push({
      id: particleId++,
      angle: (360 / 20) * i,
      distance: 30 + Math.random() * 20,
      delay: Math.random() * 0.3
    })
  }
  
  explosions.value.push(explosion)
  
  setTimeout(() => {
    explosions.value = explosions.value.filter(e => e.id !== explosion.id)
  }, 2000)
}

onMounted(() => {
  createParticles()
})
</script>

<style scoped>
@keyframes float-particle {
  0%, 100% { transform: translateY(0) translateX(0); }
  25% { transform: translateY(-20px) translateX(10px); }
  50% { transform: translateY(-10px) translateX(-5px); }
  75% { transform: translateY(-30px) translateX(15px); }
}

@keyframes trail-particle {
  0% { opacity: 1; transform: scale(1); }
  100% { opacity: 0; transform: scale(0) translateY(-20px); }
}

@keyframes explode {
  0% { opacity: 1; transform: translate(-50%, -50%) scale(1); }
  100% { opacity: 0; transform: translate(-50%, -50%) scale(0); }
}

@keyframes pulse-glow {
  0%, 100% { box-shadow: 0 0 20px rgba(59, 130, 246, 0.5); }
  50% { box-shadow: 0 0 40px rgba(147, 51, 234, 0.8); }
}

@keyframes pulse-text {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.8; }
}

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

.animate-float-particle { animation: float-particle linear infinite; }
.animate-trail-particle { animation: trail-particle 1s ease-out forwards; }
.animate-explode { animation: explode 1.5s ease-out forwards; }
.animate-pulse-glow { animation: pulse-glow 2s ease-in-out infinite; }
.animate-pulse-text { animation: pulse-text 3s ease-in-out infinite; }
.animate-fade-in-up { animation: fade-in-up 1s ease-out; }

.animation-delay-500 {
  animation-delay: 0.5s;
}
</style>