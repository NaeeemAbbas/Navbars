<template>
  <div class="font-sans antialiased text-gray-800 bg-white py-16 overflow-hidden max-w-7xl mx-auto">
    <div class="container mx-auto px-4">
      <div class="flex justify-center mb-6">
        <button class="flex items-center px-4 py-2 rounded-full border border-gray-300 text-gray-600 text-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-gray-200 transition-colors duration-200">
          Our Testimonials
        </button>
      </div>

      <h1 class="text-3xl sm:text-4xl md:text-5xl font-semibold text-center mb-4 leading-tight">
        What Our Educational Partners Say
      </h1>

      <p class="text-lg text-gray-600 text-center mb-12 mx-auto max-w-2xl">
        Discover how Xpert LMS has empowered institutions to achieve their learning objectives and elevate student success.
      </p>
    </div>

    <div class="relative py-8 overflow-hidden">
      <div class="flex flex-nowrap animate-marquee-left">
        <div
          v-for="(testimonial, index) in reviewsRow1"
          :key="'row1-' + index"
          class="flex-shrink-0 w-80 md:w-96 p-6 mr-6 bg-white rounded-3xl shadow-lg border border-gray-100 flex flex-col testimonial-card"
        >
          <div class="flex items-start mb-4">
            <img :src="testimonial.avatar" :alt="testimonial.name" class="w-12 h-12 rounded-full mr-4 object-cover">
            <div>
              <p class="font-semibold text-lg">{{ testimonial.name }}</p>
              <div class="flex text-yellow-400">
                <svg v-for="s in testimonial.stars" :key="s" class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.538 1.118l-2.8-2.034a1 1 0 00-1.176 0l-2.8 2.034c-.783.57-1.838-.197-1.538-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.381-1.81.588-1.81h3.462a1 1 0 00.95-.69l1.07-3.292z"></path>
                </svg>
              </div>
            </div>
            <svg class="w-8 h-8 text-gray-200 ml-auto -mt-2 -mr-2" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path d="M11 20H6c-1.103 0-2-.897-2-2V9c0-1.103.897-2 2-2h5c1.103 0 2 .897 2 2v7h-3l-2 2h4.001A7.986 7.986 0 0013 18c0-3.309 2.691-6 6-6s6 2.691 6 6-2.691 6-6 6c-.471 0-.931-.068-1.376-.199L17.5 22l-4.5-2h-2zM6 9h5v5H8c-.552 0-1 .448-1 1v1h2l-2 2h-.001C6.068 18 6.529 18 7 18a5.987 0 005.999-5.999V9c0-.552-.448-1-1-1H6c-.552 0-1 .448-1 1v1z" />
            </svg>
          </div>
          <p class="text-gray-700 text-sm mb-4 feedback-text" :class="{'expanded': testimonial.showFullFeedback}">
            {{ testimonial.feedback }}
          </p>
          <button
            v-if="testimonial.feedback.length > 150 && !testimonial.showFullFeedback"
            @click="toggleFullFeedback(testimonial)"
            class="text-blue-600 hover:underline text-sm mt-auto self-start"
          >
            Read More
          </button>
          <button
            v-else-if="testimonial.feedback.length > 150 && testimonial.showFullFeedback"
            @click="toggleFullFeedback(testimonial)"
            class="text-blue-600 hover:underline text-sm mt-auto self-start"
          >
            Show Less
          </button>
        </div>
      </div>

      <div class="flex flex-nowrap animate-marquee-right mt-6">
        <div
          v-for="(testimonial, index) in reviewsRow2"
          :key="'row2-' + index"
          class="flex-shrink-0 w-80 md:w-96 p-6 mr-6 bg-white rounded-3xl shadow-lg border border-gray-100 flex flex-col testimonial-card"
        >
          <div class="flex items-start mb-4">
            <img :src="testimonial.avatar" :alt="testimonial.name" class="w-12 h-12 rounded-full mr-4 object-cover">
            <div>
              <p class="font-semibold text-lg">{{ testimonial.name }}</p>
              <div class="flex text-yellow-400">
                <svg v-for="s in testimonial.stars" :key="s" class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.538 1.118l-2.8-2.034a1 1 0 00-1.176 0l-2.8 2.034c-.783.57-1.838-.197-1.538-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.381-1.81.588-1.81h3.462a1 1 0 00.95-.69l1.07-3.292z"></path>
                </svg>
              </div>
            </div>
            <svg class="w-8 h-8 text-gray-200 ml-auto -mt-2 -mr-2" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path d="M11 20H6c-1.103 0-2-.897-2-2V9c0-1.103.897-2 2-2h5c1.103 0 2 .897 2 2v7h-3l-2 2h4.001A7.986 0 0013 18c0-3.309 2.691-6 6-6s6 2.691 6 6-2.691 6-6 6c-.471 0-.931-.068-1.376-.199L17.5 22l-4.5-2h-2zM6 9h5v5H8c-.552 0-1 .448-1 1v1h2l-2 2h-.001C6.068 18 6.529 18 7 18a5.987 0 005.999-5.999V9c0-.552-.448-1-1-1H6c-.552 0-1 .448-1 1v1z" />
            </svg>
          </div>
          <p class="text-gray-700 text-sm mb-4 feedback-text" :class="{'expanded': testimonial.showFullFeedback}">
            {{ testimonial.feedback }}
          </p>
          <button
            v-if="testimonial.feedback.length > 150 && !testimonial.showFullFeedback"
            @click="toggleFullFeedback(testimonial)"
            class="text-blue-600 hover:underline text-sm mt-auto self-start"
          >
            Read More
          </button>
          <button
            v-else-if="testimonial.feedback.length > 150 && testimonial.showFullFeedback"
            @click="toggleFullFeedback(testimonial)"
            class="text-blue-600 hover:underline text-sm mt-auto self-start"
          >
            Show Less
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AutoScrollingTestimonials',
  data() {
    const baseReviews = [
      {
        name: 'Michael Brown',
        avatar: '/src/assets/img1.jpg',
        feedback: 'Capable has truly transformed how I connect with people. The interface is intuitive, and I appreciate the emphasis on genuine interactions. It\'s more than just an app; it\'s a community where I feel understood and can easily share my experiences. Highly recommended!',
        stars: 5,
      },
      {
        name: 'Emily Johnson',
        avatar: '/src/assets/img1.jpg',
        feedback: 'I was hesitant at first, but Capable exceeded all my expectations. Finding like-minded individuals has never been easier, and the events feature is a game-changer. I\'ve attended several virtual meetups and made some incredible friends.',
        stars: 5,
      },
      {
        name: 'John Doe',
        avatar: '/src/assets/img1.jpg',
        feedback: 'The design is sleek, and the app is incredibly responsive. What I love most about Capable is its commitment to user privacy and safety. I feel secure while engaging with new people.',
        stars: 5,
      },
      {
        name: 'James Taylor',
        avatar: '/src/assets/img1.jpg',
        feedback: 'The community support and engaging multimedia sharing on Capable have made it my favorite platform for connecting and sharing. It\'s dynamic and always something new to explore.',
        stars: 5,
      },
      {
        name: 'Laura Martinez',
        avatar: '/src/assets/img.jpg',
        feedback: 'I\'m amazed at how Capable\'s advanced privacy controls and customizable features have enhanced my online social experience. Truly innovative and user-friendly! This is a longer feedback to test the "Read More" functionality. It should definitely exceed the line limit and trigger the button. I hope it works well for demonstration.',
        stars: 5,
      },
      {
        name: 'David Wilson',
        avatar: '/src/assets/img1.jpg',
        feedback: 'Capable provides a seamless way to meet new people and discover shared interests. The app is fast, reliable, and genuinely helps foster new relationships in a positive environment.',
        stars: 5,
      },
    ];

    // Add `showFullFeedback` property to each testimonial for individual toggle state
    const processedReviews = baseReviews.map(review => ({
      ...review,
      showFullFeedback: false,
    }));

    return {
      reviewsRow1: [...processedReviews, ...processedReviews],
      reviewsRow2: [...processedReviews.slice(2), ...processedReviews.slice(0, 2), ...processedReviews.slice(2), ...processedReviews.slice(0, 2)],
    };
  },
  methods: {
    toggleFullFeedback(testimonial) {
      testimonial.showFullFeedback = !testimonial.showFullFeedback;
    }
  }
};
</script>

<style scoped>
/* Keyframe animation for moving left */
@keyframes marquee-left {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-50%); /* Half the width of duplicated content */
  }
}

/* Keyframe animation for moving right */
@keyframes marquee-right {
  0% {
    transform: translateX(-50%); /* Start from the "end" of the duplicated content */
  }
  100% {
    transform: translateX(0%); /* Move back to the start */
  }
}

.animate-marquee-left {
  animation: marquee-left 40s linear infinite; /* Adjust duration as needed */
  animation-play-state: running;
}

.animate-marquee-left:hover {
  animation-play-state: paused;
}

.animate-marquee-right {
  animation: marquee-right 40s linear infinite; /* Adjust duration as needed */
  animation-play-state: running;
}

.animate-marquee-right:hover {
  animation-play-state: paused;
}

/* --- Card Sizing and Text Truncation --- */

.testimonial-card {
  /* Set a fixed height for all cards */
  height: 280px; /* Adjust this value as needed */
  transition: height 0.3s ease-in-out; /* Smooth transition for height changes */
}

.feedback-text {
  /* Limit text to a certain number of lines */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 5; 
  overflow: hidden;
  text-overflow: ellipsis;
}

.feedback-text.expanded {
  -webkit-line-clamp: unset; /* Remove line clamp to show full text */
  overflow: visible; /* Allow content to be visible */
}

/* If you want the card to expand when "Read More" is clicked, remove the fixed height from .testimonial-card
   and manage its height dynamically or let content dictate it when expanded.
   However, this might break the smooth marquee effect if cards change height dynamically.
   A better approach for showing full text is usually a modal.
   For this example, the fixed height remains, and clicking "Read More" will just remove the ellipsis,
   but the text will overflow the card if it's too long, or you can make the card's height auto.
   If you want the card to expand, change .testimonial-card height to auto or max-height in .expanded state.
*/

/* Example for expanding card height with "Read More" (optional, uncomment to try) */
.testimonial-card.expanded-card {
   height: auto;
   max-height: 500px; /* Or a sufficiently large value */
}
</style>