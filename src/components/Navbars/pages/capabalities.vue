<template>
  <div class="relative py-16 px-4 sm:px-6 lg:px-8 overflow-hidden bg-gray-50 ">
    <div class="max-w-7xl mx-auto">
      <div class="relative z-10 lg:grid lg:grid-cols-2 lg:items-center">
        <div class="lg:col-span-1 flex justify-center lg:justify-start">
          <div class="relative w-[400px] h-[550px] bg-white rounded-2xl shadow-xl p-6 overflow-hidden border border-gray-200">
            <div class="flex border-b border-gray-200 mb-6">
              <button class="px-4 py-2 text-sm font-medium text-purple-600 border-b-2 border-purple-600 focus:outline-none">
                Reach
              </button>
              <button class="px-4 py-2 text-sm font-medium text-gray-500 hover:text-gray-700 focus:outline-none">
                Engagements
              </button>
              <button class="px-4 py-2 text-sm font-medium text-gray-500 hover:text-gray-700 focus:outline-none">
                Audience
              </button>
            </div>

            <div class="mb-8">
              <div class="flex items-center text-gray-500 text-sm mb-4">
                <span>Reach</span>
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 ml-1 cursor-pointer" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>

              <h4 class="text-gray-800 font-semibold mb-3">Accounts reached</h4>
              <div class="relative w-full bg-gray-200 rounded-full h-2.5 mb-2">
                <div class="bg-purple-500 h-2.5 rounded-full" style="width: 85%;"></div>
              </div>
              <p class="text-sm text-gray-600 mb-6">Followers</p>

              <h4 class="text-gray-800 font-semibold mb-3">Non-followers</h4>
              <div class="relative w-full bg-gray-200 rounded-full h-2.5">
                <div class="bg-purple-500 h-2.5 rounded-full" style="width: 18.1%;"></div>
                <span class="absolute right-0 top-1/2 -translate-y-1/2 mr-2 text-xs font-bold text-gray-800">18.1%</span>
              </div>
            </div>

            <div class="absolute right-4 top-20 w-64 bg-white rounded-lg shadow-xl p-4 border border-gray-100 transform rotate-3 origin-bottom-right">
              <h3 class="text-lg font-bold text-gray-800 mb-4">Message</h3>
              <div class="space-y-4">
                <div class="flex items-center">
                  <img src="/src//assets/img2.jpg" alt="John Doe" class="w-10 h-10 rounded-full mr-3" />
                  <div>
                    <p class="font-semibold text-gray-800">John Doe</p>
                    <p class="text-sm text-gray-500">Hi Angelina! How are you?</p>
                  </div>
                </div>
                <div class="flex items-center">
                  <img src="/src//assets/img1.jpg" alt="Courtney Henry" class="w-10 h-10 rounded-full mr-3" />
                  <div>
                    <p class="font-semibold text-gray-800">Courtney Henry</p>
                    <p class="text-sm text-gray-500">Do you need that design?</p>
                  </div>
                </div>
                 <div class="flex items-center">
                  <img src="/src//assets/img.jpg" alt="Jerome Bell" class="w-10 h-10 rounded-full mr-3" />
                  <div>
                    <p class="font-semibold text-gray-800">Jerome Bell</p>
                    <p class="text-sm text-gray-500">What is the price of houry...</p>
                  </div>
                </div>
                 <div class="flex items-center">
                  <img src="/src//assets/img2.jpg" alt="Arlene McCoy" class="w-10 h-10 rounded-full mr-3" />
                  <div>
                    <p class="font-semibold text-gray-800">Arlene McCoy</p>
                    <p class="text-sm text-gray-500">Awesome!</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="lg:col-span-1 mt-12 lg:mt-0">
          <h2 class="text-3xl sm:text-4xl  md:text-5xl font-semibold text-gray-900  mb-8">
            Getting Started with Xpert LMS
          </h2>
          <p class="text-xl text-gray-600 mb-10">
            Follow these simple steps to set up your institution and empower your learning community.
          </p>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
            <div class="bg-white rounded-lg shadow-sm p-5 flex items-start space-x-4 border border-gray-100 hover:shadow-md transition-shadow duration-300 bg-dots">
              <div class="bg-purple-100 p-3 rounded-2xl flex-shrink-0">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 text-purple-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M9.75 17L9 20l-1 1h4c0 0 0 0 0 0h5.25A1.75 1.75 0 0020 19.25V5.75A1.75 1.75 0 0018.25 4H5.75A1.75 1.75 0 004 5.75v12.5A1.75 1.75 0 005.75 20z" />
                </svg>
              </div>
              <p class="text-lg text-gray-700 font-medium">Set Up Your Institution</p>
            </div>

            <div class="bg-white rounded-lg shadow-sm p-5 flex items-start space-x-4 border border-gray-100 hover:shadow-md transition-shadow duration-300 bg-dots">
              <div class="bg-purple-100 p-3 rounded-full flex-shrink-0">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 text-purple-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.828 0L6.343 16.657m0 0A1.998 1.998 0 013.515 14L2 15.515A2 2 0 002 18h15a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v4m16-4a2 2 0 00-2-2H5a2 2 0 00-2 2v4m16-4a2 2 0 00-2-2H5a2 2 0 00-2 2v4" />
                </svg>
              </div>
              <p class="text-lg text-gray-700 font-medium">Enroll Students & Faculty</p>
            </div>

            <div class="bg-white rounded-lg shadow-sm p-5 flex items-start space-x-4 border border-gray-100 hover:shadow-md transition-shadow duration-300 bg-dots">
              <div class="bg-purple-100 p-3 rounded-full flex-shrink-0">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 text-purple-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
                </svg>
              </div>
              <p class="text-lg text-gray-700 font-medium">Launch & Engage.</p>
            </div>

            <div class="bg-white rounded-lg shadow-sm p-5 flex items-start space-x-4 border border-gray-100 hover:shadow-md transition-shadow duration-300 bg-dots">
              <div class="bg-purple-100 p-3 rounded-full flex-shrink-0">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 text-purple-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z" />
                </svg>
              </div>
              <p class="text-lg text-gray-700 font-medium">Publish courses.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Data for the inlined Message Box Overlay
const messages = ref([
  { name: 'John Doe', message: 'Hi Angelina! How are you?' },
  { name: 'Courtney Henry', message: 'Do you need that design?' },
  { name: 'Jerome Bell', message: 'What is the price of houry...' },
  { name: 'Arlene McCoy', message: 'Awesome!' },
]);

// Note: No specific reactive data needed for the progress bars as their widths are hardcoded.
</script>

<style scoped>
/* Dotted background pattern */

</style>