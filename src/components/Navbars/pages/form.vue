<template>
  <div class="bg-[#F8F9FA] p-8 py-16 text-black flex justify-center items-center">
    <div class="w-full max-w-md bg-white rounded-lg shadow-xl p-8">
    
      <form @submit.prevent="handleSubmit">
        <div class="mb-5">
          <label for="name" class="block text-gray-700 text-sm font-medium mb-2">Your Name</label>
          <input
            type="text"
            id="name"
            v-model="formData.name"
            class="w-full px-4 py-3 bg-white border border-gray-300 rounded-md focus:outline-none focus:border-blue-500 focus:ring-1 focus:ring-blue-500 text-gray-900 placeholder-gray-400"
            placeholder="John Doe"
            required
          />
        </div>

        <div class="mb-5">
          <label for="email" class="block text-gray-700 text-sm font-medium mb-2">Email Address</label>
          <input
            type="email"
            id="email"
            v-model="formData.email"
            class="w-full px-4 py-3 bg-white border border-gray-300 rounded-md focus:outline-none focus:border-blue-500 focus:ring-1 focus:ring-blue-500 text-gray-900 placeholder-gray-400"
            placeholder="your.email@example.com"
            required
          />
        </div>

        <div class="mb-5">
          <label for="subject" class="block text-gray-700 text-sm font-medium mb-2">Subject</label>
          <div class="relative">
            <select
              id="subject"
              v-model="formData.subject"
              class="w-full px-4 py-3 appearance-none bg-white border border-gray-300 rounded-md focus:outline-none focus:border-blue-500 focus:ring-1 focus:ring-blue-500 text-gray-900 pr-10"
              required
            >
              <option value="" disabled>Select a subject</option>
              <option value="General Inquiry">General Inquiry</option>
              <option value="Technical Support">Technical Support</option>
              <option value="Billing Question">Billing Question</option>
              <option value="Partnership Opportunity">Partnership Opportunity</option>
              <option value="Other">Other</option>
            </select>
            <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
              <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
            </div>
          </div>
        </div>

        <div class="mb-6">
          <label for="message" class="block text-gray-700 text-sm font-medium mb-2">Your Message</label>
          <textarea
            id="message"
            v-model="formData.message"
            rows="5"
            class="w-full px-4 py-3 bg-white border border-gray-300 rounded-md focus:outline-none focus:border-blue-500 focus:ring-1 focus:ring-blue-500 text-gray-900 placeholder-gray-400 resize-y"
            placeholder="How can we help you?"
            required
          ></textarea>
        </div>

        <button
          type="submit"
          class="w-full bg-[#5C6BC0] text-white font-bold py-3 px-4 rounded-md hover:bg-[#4C5AA0] transition duration-300 focus:outline-none focus:ring-2 focus:ring-[#5C6BC0] focus:ring-offset-2 focus:ring-offset-white"
        >
          Send Message
        </button>
      </form>

      <p v-if="formSubmitted" class="text-green-600 text-center mt-4 text-sm">Thank you for your message! We will get back to you soon.</p>
      <p v-if="formError" class="text-red-600 text-center mt-4 text-sm">An error occurred. Please try again later.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactForm',
  data() {
    return {
      formData: {
        name: '',
        email: '',
        subject: '', // Changed to empty string to match "Select a subject" initial state
        message: '',
      },
      formSubmitted: false,
      formError: false,
    };
  },
  methods: {
    handleSubmit() {
      // For demonstration, log data and simulate success/error
      console.log('Form Submitted:', this.formData);

      // In a real application, you would send this data to a backend server.
      // Example using fetch API (requires a server endpoint):
      /*
      fetch('/api/contact', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify(this.formData),
      })
      .then(response => {
        if (!response.ok) {
          throw new Error('Network response was not ok');
        }
        return response.json();
      })
      .then(data => {
        console.log('Success:', data);
        this.formSubmitted = true;
        this.formError = false;
        // Clear the form
        this.formData = {
          name: '',
          email: '',
          subject: '',
          message: '',
        };
      })
      .catch((error) => {
        console.error('Error:', error);
        this.formError = true;
        this.formSubmitted = false;
      });
      */

      // --- SIMULATION ONLY ---
      this.formSubmitted = true;
      this.formError = false;
      // Optionally clear the form after a successful submission simulation
      setTimeout(() => {
        this.formData = {
          name: '',
          email: '',
          subject: '',
          message: '',
        };
        // Reset message after some time
        setTimeout(() => {
          this.formSubmitted = false;
        }, 3000);
      }, 1000);
      // --- END SIMULATION ---
    },
  },
};
</script>

<style scoped>
/* No additional scoped styles needed as Tailwind handles most of it */
/* Custom styling for the select dropdown arrow might be needed for absolute precision */
</style>