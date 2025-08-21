<template>
  <footer class="bg-[#9810FA] text-gray-300 py-12 relative">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 border-b border-gray-700 pb-10 mb-8">

        <div class="flex flex-col items-center md:items-start text-center md:text-left">
          <div class="flex items-center justify-center">
            <!-- <img :src="logo" alt="SATA Technologies Logo" class="w-10 sm:w-14 mb-4"> -->
            <h1 class="text-white text-3xl font-bold">
              Xpert Lms
            </h1>
          </div>
          <p class="text-sm leading-relaxed mb-4">
            We are the best World Information Technology Company. Providing the highest quality.
          </p>
          <div class="flex space-x-3">
            <a href="#" aria-label="Facebook" class="w-9 h-9 flex items-center justify-center border border-gray-500 text-gray-300 hover:bg-gray-700 transition-colors duration-200">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M9 8h-3v4h3v12h5v-12h3.642l.358-4h-4v-1.667c0-.955.248-1.333 1.143-1.333h2.857v-5h-3.125c-3.259 0-4.875 1.717-4.875 4.667v2.333z"/></svg>
            </a>
            <a href="#" aria-label="Instagram" class="w-9 h-9 flex items-center justify-center border border-gray-500 text-gray-300 hover:bg-gray-700 transition-colors duration-200">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.772 1.66 4.904 4.904.058 1.267.069 1.647.069 4.85 0 3.204-.012 3.584-.07 4.85-0.132 3.252-1.65 4.772-4.904 4.904-1.267.058-1.647.069-4.85.069s-3.584-.012-4.85-.07c-3.252-0.132-4.772-1.65-4.904-4.904-0.058-1.267-0.069-1.647-0.069-4.85s0.012-3.584.07-4.85c0.132-3.252 1.65-4.772 4.904-4.904 1.267-0.058 1.647-0.069 4.85-0.069zm0-2.163c-3.259 0-3.668.014-4.949.072-4.358.2-6.78 2.618-6.98 6.98-0.059 1.281-0.073 1.691-0.073 4.949s0.014 3.668 0.072 4.949c0.2 4.358 2.618 6.78 6.98 6.98 1.281 0.059 1.691 0.073 4.949 0.073s3.668-0.014 4.949-0.072c4.354-0.2 6.782-2.618 6.979-6.98 0.059-1.281 0.073-1.691 0.073-4.949s-0.014-3.668-0.072-4.949c-0.198-4.358-2.618-6.78-6.979-6.98-1.281-0.059-1.691-0.073-4.949-0.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.162 6.162 6.162 6.162-2.759 6.162-6.162c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.791-4-4s1.791-4 4-4 4 1.791 4 4c0 2.209-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
            </a>
            <a href="#" aria-label="Pinterest" class="w-9 h-9 flex items-center justify-center border border-gray-500 text-gray-300 hover:bg-gray-700 transition-colors duration-200">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm-2.435 15.688c-.611-.088-.867-.532-.387-1.163.48-.631 2.222-2.768 2.222-2.768s-.331-.795-.276-1.554c.056-.76.438-1.396 1.077-1.396 1.018 0 1.637.765 1.637 1.84 0 1.096-.549 2.57-.828 3.527-.279.956.883 1.713 1.884 1.341 2.454-.913 3.664-4.885 2.544-6.42-.992-1.37-3.033-2.617-5.592-2.617-4.14 0-6.953 2.981-6.953 6.408 0 3.197 2.091 5.961 4.908 5.961 1.053 0 1.954-.539 2.288-1.285.14-.306.079-.569-.204-.88-.415-.468-.97-.736-1.114-.997-.367-.655-.164-1.233.407-2.126.657-1.023.758-.918 1.258-.291.5.626.865 1.583.865 2.651 0 1.986-1.144 3.738-2.671 4.195z"/></svg>
            </a>
            <a href="#" aria-label="LinkedIn" class="w-9 h-9 flex items-center justify-center border border-gray-500 text-gray-300 hover:bg-gray-700 transition-colors duration-200">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.761 0 5-2.239 5-5v-14c0-2.761-2.239-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
            </a>
          </div>
        </div>

        <div>
          <h4 class="text-xl font-semibold mb-4 text-white">Quick Links</h4>
          <ul>
            <li v-for="link in quickLinks" :key="link.text" class="mb-2">
              <a :href="link.url" class="flex items-center text-gray-400 hover:text-white transition-colors duration-200">
                <span class="mr-2 text-gray-500">—</span> {{ link.text }}
              </a>
            </li>
          </ul>
        </div>

        <div>
          <h4 class="text-xl font-semibold mb-4 text-white">Contacts</h4>
          <p class="mb-2">
            <span class="font-medium text-white">Address:</span> Ahmed Plaza, Main Alamdar Chowk Danyore Gilgit
          </p>
          <p class="mb-2">
            <span class="font-medium text-white">Phone:</span> +92 3133898836
          </p>
          <p class="mb-2">
            <span class="font-medium text-white">Fax:</span> +92 3133879645
          </p>
          <p class="mb-2">
            <span class="font-medium text-white">Email:</span> <a href="mailto:info@sata.pk" class="hover:underline">info@sata.pk</a>
          </p>
          <p class="mb-2">
            <span class="font-medium text-white">Website:</span> <a href="http://www.sata.pk" target="_blank" rel="noopener noreferrer" class="hover:underline">www.sata.pk</a>
          </p>
        </div>

      </div>

      <div class="flex flex-col md:flex-row md:justify-between items-center text-center md:text-left text-sm text-gray-500">
        <p class="mb-4 md:mb-0">© 2024 - SATA Technologies Pvt. Ltd. All rights reserved.</p>
        <nav>
          <ul class="flex flex-wrap justify-center space-x-6">
            <li><a href="#" class="hover:text-white transition-colors duration-200">About Us</a></li>
            <li><a href="#" class="hover:text-white transition-colors duration-200">Privacy Policy</a></li>
            <li><a href="#" class="hover:text-white transition-colors duration-200">Services</a></li>
          </ul>
        </nav>
      </div>
    </div>

    <button
      @click="scrollToTop"
      v-show="showScrollToTopButton"
      class="fixed bottom-8 right-8 bg-[#C82C95] text-white p-3 rounded-full shadow-lg hover:bg-pink-600 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2 transition-colors duration-300 z-50"
    >
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18"></path>
      </svg>
    </button>
  </footer>
</template>

<script>
// import logo from '../../../assets/img1.jpg'
export default {
  name: 'AppFooter',
  data() {
    return {
      showScrollToTopButton: false, // New data property to control visibility
      quickLinks: [
        { text: 'Solutions', url: '#' },
        { text: 'Features', url: '#' },
        { text: 'How It Works', url: '#' },
        { text: 'Pricing', url: '#' },
        { text: 'Contact Us', url: '#' },
        { text: 'Blog', url: '#' },
      ],
    };
  },
  methods: {
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    },
    handleScroll() {
      // Show button if scrolled more than 200px from top
      // Adjust '200' as needed for when you want the button to appear.
      this.showScrollToTopButton = window.scrollY > 200;
    }
  },
  mounted() {
    // Add the scroll event listener when the component is mounted
    window.addEventListener('scroll', this.handleScroll);
    // Call it once on mount to set initial state
    this.handleScroll();
  },
  beforeUnmount() {
    // Remove the scroll event listener when the component is about to be unmounted
    window.removeEventListener('scroll', this.handleScroll);
  }
};
</script>

<style scoped>
/* No additional scoped styles are strictly necessary as Tailwind covers most needs. */
/* The social icon borders are handled by Tailwind classes. */
</style>