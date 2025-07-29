<template>
  <div class="bg-[#FFFFFF] text-black p-8 relative overflow-hidden">
    <div class="absolute inset-0 bg-cover bg-center opacity-20"
         style="background-image: url('your-nust-building-background-image.jpg');">
    </div>
    <div class="absolute inset-0 bg-[#FFFFFF] opacity-80"></div>

    <div class="relative z-10 grid grid-cols-1 md:grid-cols-3 gap-8 max-w-7xl mx-auto">
      <div>
        <h3 class="text-xl font-semibold mb-4">In Focus</h3>
        <ul>
          <li class="mb-2" v-for="item in inFocusLinks" :key="item.text">
            <a :href="item.link" class="flex items-center hover:text-yellow-400 transition-colors">
              <span class="mr-2">&gt;</span> {{ item.text }}
            </a>
          </li>
        </ul>
      </div>

      <div>
        <h3 class="text-xl font-semibold mb-4">Quick Links</h3>
        <ul>
          <li class="mb-2" v-for="item in quickLinks" :key="item.text">
            <a :href="item.link" class="flex items-center hover:text-yellow-400 transition-colors">
              <span class="mr-2">&gt;</span> {{ item.text }}
            </a>
          </li>
        </ul>
      </div>

      <div>
        <h3 class="text-xl font-semibold mb-4">NUST UAN</h3>
        <p class="flex items-center mb-6">
          <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
            <path d="M20 15.5c-1.25 0-2.45-.27-3.57-.79-.34-.13-.71-.05-1.01.21l-2.2 2.2c-2.83-1.44-5.15-3.75-6.59-6.59l2.2-2.2c.26-.3.34-.67.21-1.01C8.77 6.45 8.5 5.25 8.5 4c0-.55-.45-1-1-1H4c-.55 0-1 .45-1 1 0 9.39 7.61 17 17 17 .55 0 1-.45 1-1v-3.5c0-.55-.45-1-1-1z"/>
          </svg>
          +92-51-111-11-6878
        </p>

        <h3 class="text-xl font-semibold mb-4">Address</h3>
        <p>National University of Sciences & Technology (NUST) Campus, Sector H-12, Islamabad, Pakistan</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FooterLinks',
  data() {
    return {
      inFocusLinks: [
        { text: 'NUST at a Glance', link: '#' },
        { text: 'Academic Calender', link: '#' },
        { text: 'Academic Schedule', link: '#', highlight: true }, // Added highlight property
        { text: 'Student Helplines', link: '#' },
        { text: 'Facilities at NUST', link: '#' },
        { text: 'Contact Us', link: '#' },
        { text: 'Trademark Notice', link: '#' },
        { text: 'Offices and Resources', link: '#' },
        { text: 'Marketing and Guidelines', link: '#' },
        { text: 'World Political Map', link: '#' },
      ],
      quickLinks: [
        { text: 'Innovation & Commercialisation', link: '#' },
        { text: 'Library', link: '#' },
        { text: 'Downloads', link: '#' },
        { text: "Defaulter's list", link: '#' },
        { text: 'Grievances Review Committee', link: '#' },
        { text: 'Tender Information', link: '#' },
        { text: 'Feedback', link: '#' },
        { text: 'NUST Anti-Harassment Helpline', link: '#' },
        { text: 'Online Degree/Transcript Verification', link: '#' },
        { text: 'Career Development Centre', link: '#' },
      ],
    };
  },
};
</script>

<style scoped>
/* You can add specific styles here if needed, but Tailwind handles most of it. */
/* The highlight for "Academic Schedule" can be done directly in the template. */

.hover\:text-yellow-400:hover {
  color: #FACC15; /* Tailwind's yellow-400 */
}
</style>