<template>
  <div class="font-sans antialiased text-gray-800 bg-white py-16">
    <div class="container mx-auto px-4 max-w-4xl">
      <div class="flex justify-center mb-6">
        <button class="flex items-center px-4 py-2 rounded-full border border-gray-300 text-gray-600 text-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-gray-200 transition-colors duration-200">
          
         Common Questions
        </button>
      </div>

      <h1 class="text-3xl sm:text-4xl  md:text-5xl font-semibold text-center mb-12 leading-tight">
        Frequently Asked Questions
      </h1>

      <div class="space-y-4 ">
        <div v-for="(faq, index) in faqs" :key="index" class="bg-[#F4F7F9] rounded-xl shadow-sm border border-gray-100">
          <button
            @click="toggleFAQ(index)"
            class="flex justify-between items-center w-full px-6 py-4 text-left focus:outline-none cursor-pointer"
            :aria-expanded="faq.isOpen ? 'true' : 'false'"
            :aria-controls="`faq-content-${index}`"
          >
            <span class="text-lg font-semibold text-gray-800">{{ faq.question }}</span>
            <span
              :class="{
                'transform rotate-45': faq.isOpen,
                'transition-transform duration-300': true
              }"
            >
              <svg class="w-6 h-6 bg-black rounded-4xl text-white " fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"></path>
              </svg>
            </span>
          </button>
          <div
            v-show="faq.isOpen"
            :id="`faq-content-${index}`"
            class="px-6 pb-4 pt-0 text-gray-600 text-base leading-relaxed border-t border-gray-100 mx-6"
          >
            {{ faq.answer }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FAQSection',
  data() {
    return {
      faqs: [
        {
          question: 'How do I integrate Xpert LMS with existing systems (SIS, HRIS)?',
          answer: 'Creating an account on Capable is simple! Just download the app, click on "Sign Up," and follow the prompts to enter your details, verify your email, and set up your profile. You\'ll be ready to connect in minutes!',
          isOpen: false,
        },
        {
          question: 'What kind of support is available for Xpert LMS users?',
          answer: 'Absolutely! Capable offers extensive profile customization options. You can add a profile picture, write a bio, list your interests, and even link to your social media. Make your profile uniquely yours to attract like-minded connections.',
          isOpen: false,
        },
        {
          question: 'Is Xpert LMS compliant with educational data privacy regulations',
          answer: 'Yes, Capable is designed to be fully cross-platform. Our app is available on iOS and Android devices, and you can also access most features through our web portal on any modern browser.',
          isOpen: false,
        },
        {
          question: 'Can I customize the look and feel of my institutions Xpert LMS portal?',
          answer: 'Your privacy is our priority. Capable provides robust privacy controls, allowing you to manage who can see your profile, send you messages, and view your activity. You can adjust these settings at any time in your account settings.',
          isOpen: false,
        },
        {
          question: 'What are the technical requirements for running Xpert LMS?',
          answer: 'Our smart matching algorithm uses your interests, activities, and stated preferences to suggest compatible connections. The more information you provide, the better our system can help you find relevant individuals and groups.',
          isOpen: false,
        },
        {
          question: 'How does Xpert LMS handle course creation and content management?',
          answer: 'Yes, Capable supports sharing various multimedia content, including photos, videos, and audio clips. You can upload these directly to your profile, share them in chats, or post them to your feed for your connections to see.',
          isOpen: false,
        },
        {
          question: 'Do you offer training for faculty and administrators?',
          answer: 'If you encounter any issues, our dedicated support team is here to help! You can reach us through the "Help & Support" section within the app, or visit our website for troubleshooting guides and direct contact options.',
          isOpen: false,
        },
      ],
    };
  },
  methods: {
    toggleFAQ(index) {
      // Close all other FAQs and open the clicked one, or close it if already open
      this.faqs.forEach((faq, i) => {
        if (i === index) {
          faq.isOpen = !faq.isOpen;
        } else {
          faq.isOpen = false; // Close others
        }
      });
    },
  },
};
</script>

<style scoped>
/* No custom styles needed, Tailwind handles it! */
</style>