<template>
  <div class="min-h-screen">
    <!-- Background -->
    <div class="absolute inset-0 bg-gradient-to-r from-purple-400 via-pink-500 to-red-500"></div>
    
    <!-- Glass Navbar -->
    <nav class="relative">
      <div class="absolute inset-0 bg-white/10 backdrop-blur-md border-b border-white/20"></div>
      <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <!-- Logo -->
          <div class="flex items-center space-x-2">
            <SparklesIcon class="w-8 h-8 text-white" />
            <a href="/" class="text-2xl font-bold text-white">GlassUI</a>
          </div>

          <!-- Navigation Links -->
          <div class="hidden md:flex items-center space-x-8">
            <a href="/" class="text-white/90 hover:text-white transition-colors">Home</a>
            <a href="/portfolio" class="text-white/90 hover:text-white transition-colors">Portfolio</a>
            <a href="/services" class="text-white/90 hover:text-white transition-colors">Services</a>
            <a href="/blog" class="text-white/90 hover:text-white transition-colors">Blog</a>
            <a href="/contact" class="text-white/90 hover:text-white transition-colors">Contact</a>
          </div>

          <!-- CTA Button -->
          <div class="hidden md:block">
            <button class="bg-white/20 backdrop-blur-sm text-white px-6 py-2 rounded-full border border-white/30 hover:bg-white/30 transition-all duration-300">
              Get Started
            </button>
          </div>
        </div>
      </div>
    </nav>

    <!-- Content -->
    <div class="relative pt-16 px-8 text-white">
      <h2 class="text-4xl font-bold mb-4">Glass Morphism Design</h2>
      <p class="text-white/80 text-lg">Beautiful glassmorphism navbar with backdrop blur effect.</p>
      <div class="mt-8 p-6 bg-white/10 backdrop-blur-sm rounded-lg border border-white/20">
        <h3 class="text-xl font-semibold mb-2">Features</h3>
        <ul class="space-y-2 text-white/90">
          <li>• Backdrop blur effect</li>
          <li>• Semi-transparent background</li>
          <li>• Modern glass aesthetic</li>
          <li>• Smooth hover transitions</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
import { Sparkles as SparklesIcon } from 'lucide-vue-next'
</script>

<style scoped>
.backdrop-blur-md {
  backdrop-filter: blur(12px);
}

.backdrop-blur-sm {
  backdrop-filter: blur(4px);
}

.transition-colors {
  transition: color 0.2s ease-in-out;
}
</style>