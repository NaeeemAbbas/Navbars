<template>
  <div class="relative py-16 px-4 sm:px-6 lg:px-8 overflow-hidden bg-gray-50">
    <div class="max-w-7xl mx-auto">
      <div class="relative z-10 lg:grid lg:grid-cols-2 lg:gap-16 lg:items-center">
        <div class="lg:col-span-1">
          <h2 class="text-3xl sm:text-4xl  md:text-5xl font-semibold text-gray-900  mb-8">
           Transform Your Learning Ecosystem Today
          </h2>
          <ul class="space-y-6 text-xl text-gray-700 ">
            <li class="flex items-start">
              <span class="flex-shrink-0 mr-3 text-purple-600">
                <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              </span>
              <span>A student dashboard view</span>
            </li>
            <li class="flex items-start">
              <span class="flex-shrink-0 mr-3 text-purple-600">
                <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              </span>
              <span>A course content page</span>
            </li>
            <li class="flex items-start">
              <span class="flex-shrink-0 mr-3 text-purple-600">
                <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              </span>
              <span>A teacher's grading interface</span>
            </li>
            <li class="flex items-start">
              <span class="flex-shrink-0 mr-3 text-purple-600">
                <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              </span>
              <span>Enhanced privacy controls for secure interactions.</span>
            </li>
            <li class="flex items-start">
              <span class="flex-shrink-0 mr-3 text-purple-600">
                <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              </span>
              <span>Intuitive interface for effortless navigation.</span>
            </li>
          </ul>

          <div class="mt-10 flex flex-col sm:flex-row gap-4 ">
            <a href="#" class="inline-flex">
              <img src="https://upload.wikimedia.org/wikipedia/commons/3/3c/Download_on_the_App_Store_Badge.svg" alt="Download on the App Store" class="h-14" />
            </a>
            <a href="#" class="inline-flex">
              <img src="https://upload.wikimedia.org/wikipedia/commons/7/78/Google_Play_Store_badge_EN.svg" alt="Get it on Google Play" class="h-14" />
            </a>
          </div>
        </div>

        <div class="lg:col-span-1 mt-12 lg:mt-0 flex justify-center lg:justify-end ">
          <div class="relative w-80 h-[560px] bg-black rounded-[3rem] shadow-2xl overflow-hidden
                      border-[10px] border-gray-900 flex flex-col justify-between p-2">
            <div class="absolute top-0 left-1/2 -translate-x-1/2 w-28 h-6 bg-black rounded-b-xl z-20"></div>

            <div class="flex-grow bg-white rounded-[2.5rem] overflow-hidden flex flex-col pt-4 pb-2 relative">
              <div class="absolute top-2 left-0 right-0 px-4 flex justify-between items-center text-gray-800 text-sm z-10">
                <span class="font-semibold">9:41</span>
                <div class="flex items-center space-x-1">
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M12 5l7 7-7 7"></path></svg>
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z"></path></svg>
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"></path></svg>
                </div>
              </div>

              <div class="flex px-4 py-2 overflow-x-auto space-x-3 scrollbar-hide">
                <div v-for="(story, index) in stories" :key="index" class="flex-shrink-0 text-center">
                  <div class="w-14 h-14 rounded-full border-2 border-purple-500 overflow-hidden flex items-center justify-center">
                    <img :src="story.imageUrl" :alt="story.alt" class="w-full h-full object-cover" />
                  </div>
                  <p class="text-xs text-gray-700 mt-1">{{ story.name }}</p>
                </div>
              </div>

              <div class="flex-grow overflow-y-auto mt-4 px-4 pb-4 scrollbar-hide">
                <div class="flex items-center mb-3">
                  <img src="/src//assets/img.jpg" alt="User Avatar" class="w-8 h-8 rounded-full mr-3" />
                  <div>
                    <p class="font-semibold text-gray-800 text-sm">John Doe</p>
                    <p class="text-xs text-gray-500">2 hours ago</p>
                  </div>
                </div>
                <div class="w-full h-48 bg-gray-200 rounded-lg overflow-hidden mb-3">
                  <img src="/src//assets/img2.jpg" alt="Post content" class="w-full h-full object-cover" />
                </div>
                <div class="flex justify-between items-center text-gray-600 text-sm mb-2">
                  <div class="flex space-x-4">
                    <div class="flex items-center space-x-1 cursor-pointer">
                      <svg class="h-5 w-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"></path></svg>
                      <span>1.2K</span>
                    </div>
                    <div class="flex items-center space-x-1 cursor-pointer">
                      <svg class="h-5 w-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"></path></svg>
                      <span>245</span>
                    </div>
                  </div>
                  <div class="flex items-center space-x-1 cursor-pointer">
                    <svg class="h-5 w-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.684 13.321v2.53m0 0a2.7 2.7 0 003.584 3.584m-3.584-3.584a2.7 2.7 0 013.584-3.584m-3.584 3.584L15.316 6.68m0 0a2.7 2.7 0 003.584 3.584m-3.584-3.584a2.7 2.7 0 013.584-3.584m-3.584 3.584L8.684 13.321m0 0L4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"></path></svg>
                    <span>Share</span>
                  </div>
                </div>
                <p class="text-gray-800 text-sm leading-snug">
                  Enjoying this amazing view from the mountains! #nature #travel #mountains
                </p>

                <div class="mt-4 text-gray-500 text-xs">
                  <p>Another post...</p>
                  <div class="w-full h-32 bg-gray-100 rounded-lg mt-2"></div>
                </div>
              </div>

              <div class="absolute bottom-0 left-0 right-0 h-14 bg-white border-t border-gray-200 rounded-b-[2.5rem]
                          flex justify-around items-center text-gray-500 text-xs z-10">
                <div class="flex flex-col items-center">
                  <svg class="h-6 w-6 text-purple-600" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z"></path></svg>
                  Home
                </div>
                <div class="flex flex-col items-center">
                  <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path></svg>
                  Search
                </div>
                <div class="flex flex-col items-center">
                  <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v3m0 0v3m0-3h3m-3 0H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                  Add
                </div>
                <div class="flex flex-col items-center">
                  <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
                  Activity
                </div>
                <div class="flex flex-col items-center">
                  <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"></path></svg>
                  Profile
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Data for the inlined MockPhoneUI
const stories = ref([
  { imageUrl: '/src/assets/img.jpg', alt: 'User Story 1', name: 'User1' },
  { imageUrl: '/src/assets/img1.jpg', alt: 'User Story 2', name: 'User2' },
  { imageUrl: '/src/assets/img2.jpg', alt: 'User Story 3', name: 'User3' },
  { imageUrl: '/src/assets/img1.jpg', alt: 'User Story 4', name: 'User4' },
  { imageUrl: '/src/assets/img.jpg', alt: 'User Story 5', name: 'User5' },
  { imageUrl: '/src/assets/img2.jpg', alt: 'User Story 6', name: 'User6' },
]);

const postImage = ref('https://via.placeholder.com/400x300/a78bfa/ffffff?text=Scenic+View');
</script>

<style scoped>
/* Custom scrollbar hide for cleaner look on mock phone */
.scrollbar-hide::-webkit-scrollbar {
    display: none;
}
.scrollbar-hide {
    -ms-overflow-style: none; /* IE and Edge */
    scrollbar-width: none; /* Firefox */
}
</style>