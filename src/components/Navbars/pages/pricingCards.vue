<template>
  <div class="font-sans antialiased text-gray-800 bg-white py-16">
    <div class="container mx-auto px-4">
      <div class="flex justify-center mb-6">
        <button class="flex items-center px-4 py-2 rounded-full border border-gray-300 text-gray-600 text-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-gray-200 transition-colors duration-200">
          Our Pricing
        </button>
      </div>

      <h1 class="text-3xl sm:text-4xl  md:text-5xl font-semibold  text-center mb-4 leading-tight">
       Flexible Plans Tailored for Every Institution
      </h1>

      <p class="text-lg text-gray-600 text-center mb-12 max-w-2xl mx-auto">
      Select the perfect Xpert LMS plan to fit your institution's size, budget, and educational goals.
      </p>

      <div class="flex justify-center mb-12">
        <div class="inline-flex bg-gray-100 rounded-full p-1">
          <button
            @click="activePlan = 'monthly'"
            :class="[
              'px-6 py-2 rounded-full text-sm font-medium transition-colors duration-300 cursor-pointer',
              activePlan === 'monthly' ? 'bg-white shadow text-purple-700' : 'text-gray-600 hover:text-purple-700'
            ]"
          >
            Monthly
          </button>
          <button
            @click="activePlan = 'yearly'"
            :class="[
              'px-6 py-2 rounded-full text-sm font-medium transition-colors duration-300 cursor-pointer',
              activePlan === 'yearly' ? 'bg-white shadow text-purple-700' : 'text-gray-600 hover:text-purple-700'
            ]"
          >
            Yearly
          </button>
        </div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-4xl mx-auto">
        <div class="bg-white rounded-3xl shadow-xl overflow-hidden border border-gray-100 p-8 flex flex-col">
          <h2 class="md:text-5xl font-semibold mb-2">Pilot Plan</h2>
          <p class="md:text-5xl font-semibold text-gray-900 mb-2">
            $0<span class="text-xl font-medium text-gray-500">/per year</span>
          </p>
          <p class="text-gray-600 mb-8 flex-grow">Ideal for small departments or pilot programs..</p>

          <button class="w-full py-3 bg-purple-600 cursor-pointer text-white rounded-lg font-semibold text-lg hover:bg-purple-700 transition duration-300 mb-8">
            Get Started
          </button>

          <h3 class="text-lg font-semibold mb-4">What's Included</h3>
          <ul class="space-y-3">
            <li class="flex items-center text-gray-700">
              <svg class="w-5 h-5 text-green-500 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
             Basic Course Creation Tools
            </li>
            <li class="flex items-center text-gray-700">
              <svg class="w-5 h-5 text-green-500 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              Up to X Users / X Courses
            </li>
            <li class="flex items-center text-gray-700">
              <svg class="w-5 h-5 text-green-500 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              Standard Support
            </li>
            <li class="flex items-center text-gray-500">
              <svg class="w-5 h-5 text-gray-400 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              User & Role Management
            </li>
            <li class="flex items-center text-gray-500">
              <svg class="w-5 h-5 text-gray-400 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              Basic Analytics
            </li>
            <li class="flex items-center text-gray-500">
              <svg class="w-5 h-5 text-gray-400 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
             Limited Storage
            </li>
          </ul>
        </div>

        <div class="bg-white rounded-3xl shadow-xl overflow-hidden border border-gray-100 p-8 flex flex-col relative">
          <div class="absolute top-0 right-0 mt-4 mr-4 bg-purple-100 text-purple-700 text-xs font-semibold px-3 py-1 rounded-full">
            Save 20% on Yearly
          </div>
          <h2 class="md:text-5xl font-semibold mb-2">Enterprise Plan</h2>
          <p class="md:text-5xl font-semibold text-gray-900 mb-2">
            $99<span class="text-xl font-medium text-gray-500">/per year</span>
          </p>
          <p class="text-gray-600 mb-8 flex-grow">Comprehensive features for advanced learning ecosystems.</p>

          <button class="w-full py-3  bg-purple-600 text-white rounded-lg font-semibold text-lg hover:bg-purple-700 transition cursor-pointer duration-300 mb-8">
            Get Started
          </button>

          <h3 class="text-lg font-semibold mb-4">What's Included</h3>
          <ul class="space-y-3">
            <li class="flex items-center text-gray-700">
              <svg class="w-5 h-5 text-green-500 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
             Advanced Course Authoring
            </li>
            <li class="flex items-center text-gray-700">
              <svg class="w-5 h-5 text-green-500 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              Unlimited Users & Courses
            </li>
            <li class="flex items-center text-gray-700">
              <svg class="w-5 h-5 text-green-500 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              Premium 24/7 Support
            </li>
            <li class="flex items-center text-gray-700">
              <svg class="w-5 h-5 text-green-500 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              Single Sign-On (SSO)
            </li>
            <li class="flex items-center text-gray-700">
              <svg class="w-5 h-5 text-green-500 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              Advanced Analytics & Reporting
            </li>
            <li class="flex items-center text-gray-700">
              <svg class="w-5 h-5 text-green-500 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
              Ample Cloud Storage
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FlexiblePricing',
  data() {
    return {
      activePlan: 'yearly' // 'monthly' or 'yearly' - set initial active state
    };
  }
};
</script>

<style scoped>
/* No custom styles needed, Tailwind handles it! */
</style>