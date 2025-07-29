<template>
  <div class="font-sans antialiased text-gray-800 bg-white">
    <div class="container mx-auto px-4 py-12 md:py-16">
      <div class="flex justify-center mb-6 md:mb-8">
        <button class="flex items-center px-4 py-2 rounded-full border border-gray-300 text-gray-600 text-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-gray-200 transition-colors duration-200">
          <svg class="w-4 h-4 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.228 9.247a1 1 0 011.026-.016l2.998 1.999a1 1 0 010 1.632l-2.998 1.999a1 1 0 01-1.026-.016V9.247z"></path>
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14v4m-4 0h8m-12-4h8"></path>
          </svg>
          How To Use
        </button>
      </div>

      <h1 class="text-3xl sm:text-4xl  md:text-5xl font-semibold text-center mb-4 md:mb-6 leading-tight">
       Getting Started with Xpert LMS
      </h1>

      <p class="text-lg text-gray-600 text-center mb-12 md:mb-16 max-w-2xl mx-auto">
        Follow these simple steps to set up your institution and empower your learning community.
      </p>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div class="bg-white rounded-3xl shadow-xl overflow-hidden border border-gray-100 p-6 flex flex-col items-center text-center group">
          <h3 class="text-xl font-semibold mb-6 text-gray-800">Sign up and personalize your profile details.</h3>
          <div class="relative w-full max-w-[280px] aspect-[9/19] rounded-3xl overflow-hidden bg-gradient-to-br from-purple-200 to-indigo-200 shadow-lg border-2 border-transparent group-hover:border-purple-400 transition-all duration-300">
            <div class="absolute inset-0 flex flex-col p-4 text-left">
              <div class="w-1/3 h-4 bg-gray-900 rounded-b-lg mx-auto mb-2"></div>

              <div class="flex items-center mb-4 text-gray-700">
                <svg class="w-5 h-5 mr-1.5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17v2a2 2 0 01-2 2H5a2 2 0 01-2-2v-7l5-5 5 5V17z"></path>
                </svg>
                <span class="text-sm font-medium">Profile</span>
              </div>
              <div class="flex flex-col items-center mb-4">
                <div class="w-14 h-14 rounded-full bg-purple-400 flex items-center justify-center text-white text-2xl font-bold mb-1">J</div>
                <span class="text-md font-semibold text-gray-900">Jenny Key</span>
                <span class="text-xs text-gray-600">@jenny_key</span>
              </div>
              <div class="text-gray-700 text-xs mb-4">
                Effortlessly configure courses, user roles, and customize branding to fit your needs.
              </div>
              <div class="flex justify-around text-center text-gray-800 mb-4">
                <div>
                  <div class="font-bold text-md">58</div>
                  <div class="text-xs text-gray-500">Posts</div>
                </div>
                <div>
                  <div class="font-bold text-md">896</div>
                  <div class="text-xs text-gray-500">Followers</div>
                </div>
                <div>
                  <div class="font-bold text-md">387</div>
                  <div class="text-xs text-gray-500">Following</div>
                </div>
              </div>
              <button class="w-full py-1.5 bg-purple-600 text-white rounded-lg font-medium text-sm hover:bg-purple-700 transition duration-300">
                Edit Profile
              </button>
              <div class="flex justify-around mt-3 text-xs text-gray-500">
                <span>Post</span>
                <span>Media</span>
                <span>Liked</span>
              </div>
            </div>
          </div>
        </div>

        <div class="bg-white rounded-3xl shadow-xl overflow-hidden border border-gray-100 p-6 flex flex-col items-center text-center group">
          <h3 class="text-xl font-semibold mb-6 text-gray-800">Explore and send connection requests to users.</h3>
          <div class="relative w-full max-w-[280px] aspect-[9/19] rounded-3xl overflow-hidden bg-gradient-to-br from-blue-200 to-indigo-200 shadow-lg border-2 border-transparent group-hover:border-blue-400 transition-all duration-300">
            <div class="absolute inset-0 flex flex-col p-4 text-left">
              <div class="w-1/3 h-4 bg-gray-900 rounded-b-lg mx-auto mb-2"></div>

              <div class="flex items-center mb-4 text-gray-700">
                <svg class="w-5 h-5 mr-1.5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17v2a2 2 0 01-2 2H5a2 2 0 01-2-2v-7l5-5 5 5V17z"></path>
                </svg>
                <span class="text-sm font-medium">Notification</span>
              </div>
              <div class="text-xs text-gray-500 mb-3">Today</div>
              <div class="space-y-3">
                <div class="flex items-center p-2.5 bg-white rounded-lg shadow-sm">
                  <div class="w-9 h-9 rounded-full bg-gray-300 mr-2"></div>
                  <div>
                    <div class="font-medium text-gray-900 text-sm">Drip Zinnnnr</div>
                    <div class="text-xs text-gray-600">sent you a connection request.</div>
                  </div>
                </div>
                <div class="flex items-center p-2.5 bg-white rounded-lg shadow-sm">
                  <div class="w-9 h-9 rounded-full bg-gray-300 mr-2"></div>
                  <div>
                    <div class="font-medium text-gray-900 text-sm">Jerry Key</div>
                    <div class="text-xs text-gray-600">sent you a connection request.</div>
                  </div>
                </div>
              </div>
              <div class="text-xs text-gray-500 mt-4 mb-3">Wednesday</div>
               <div class="space-y-3">
                <div class="flex items-center p-2.5 bg-white rounded-lg shadow-sm">
                  <div class="w-9 h-9 rounded-full bg-gray-300 mr-2"></div>
                  <div>
                    <div class="font-medium text-gray-900 text-sm">Kimbo</div>
                    <div class="text-xs text-gray-600">sent you a connection request.</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="bg-white rounded-3xl shadow-xl overflow-hidden border border-gray-100 p-6 flex flex-col items-center text-center group">
          <h3 class="text-xl font-semibold mb-6 text-gray-800">Start chatting and share your moments.</h3>
          <div class="relative w-full max-w-[280px] aspect-[9/19] rounded-3xl overflow-hidden bg-gradient-to-br from-green-200 to-indigo-200 shadow-lg border-2 border-transparent group-hover:border-green-400 transition-all duration-300">
            <div class="absolute inset-0 flex flex-col p-4 text-left">
              <div class="w-1/3 h-4 bg-gray-900 rounded-b-lg mx-auto mb-2"></div>

              <div class="flex items-center mb-4 text-gray-700">
                <svg class="w-5 h-5 mr-1.5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17v2a2 2 0 01-2 2H5a2 2 0 01-2-2v-7l5-5 5 5V17z"></path>
                </svg>
                <span class="text-sm font-medium">Capable</span>
              </div>
              <div class="flex justify-around mb-4">
                <div class="w-9 h-9 rounded-full bg-red-400"></div>
                <div class="w-9 h-9 rounded-full bg-blue-400"></div>
                <div class="w-9 h-9 rounded-full bg-green-400"></div>
                <div class="w-9 h-9 rounded-full bg-yellow-400"></div>
              </div>
              <div class="flex flex-col space-y-3 flex-grow overflow-hidden">
                <div class="bg-white rounded-lg shadow-sm p-2.5 flex-shrink-0">
                  <div class="flex items-center mb-1">
                    <div class="w-7 h-7 rounded-full bg-gray-300 mr-2"></div>
                    <span class="font-medium text-gray-900 text-sm">Jenny Key</span>
                    <span class="text-xs text-gray-500 ml-auto">12:34 PM</span>
                  </div>
                  <p class="text-xs text-gray-700">Hey, just checking in!</p>
                </div>
                <div class="bg-white rounded-lg shadow-sm p-2.5 flex-shrink-0">
                  <div class="flex items-center mb-1">
                    <div class="w-7 h-7 rounded-full bg-gray-300 mr-2"></div>
                    <span class="font-medium text-gray-900 text-sm">Jerry Key</span>
                    <span class="text-xs text-gray-500 ml-auto">12:35 PM</span>
                  </div>
                  <p class="text-xs text-gray-700">How are you doing?</p>
                </div>
                 <div class="bg-white rounded-lg shadow-sm p-2.5 flex-shrink-0">
                  <div class="flex items-center mb-1">
                    <div class="w-7 h-7 rounded-full bg-gray-300 mr-2"></div>
                    <span class="font-medium text-gray-900 text-sm">Kimbo</span>
                    <span class="text-xs text-gray-500 ml-auto">12:36 PM</span>
                  </div>
                  <p class="text-xs text-gray-700">Let's connect soon!</p>
                </div>
              </div>
              <div class="mt-4">
                <input type="text" placeholder="Type a message..." class="w-full p-2 border border-gray-300 rounded-lg text-xs focus:outline-none focus:ring-2 focus:ring-purple-200">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GettingStarted',
};
</script>

<style scoped>
/* No custom styles needed, Tailwind handles it! */
</style>