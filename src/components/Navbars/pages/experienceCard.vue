<template>

  <div class="flex flex-wrap justify-center gap-6 p-8 bg-gray-50  overflow-hidden">
  
    <div
      ref="card1"
      class="w-full sm:w-100 p-8 bg-[#F8FAFC] rounded-3xl shadow-md flex flex-col items-center justify-center text-center transition-all duration-300 hover:shadow-lg bg-dots"
    >
      <div class="md:text-5xl font-semibold text-gray-800 mb-2">
        {{ animatedNumber1.toLocaleString() }}k+
      </div>
      <p class="text-lg text-gray-600">Institutions Transformed</p>
    </div>

    <div
      ref="card2"
      class="w-full sm:w-80 p-8 bg-[#F8FAFC]  rounded-lg shadow-md flex flex-col items-center justify-center text-center transition-all duration-300 hover:shadow-lg bg-dots"
    >
      <div class="md:text-5xl font-semibold text-gray-800 mb-2">
        {{ animatedNumber2.toLocaleString() }}k+
      </div>
      <p class="text-lg text-gray-600">Active Learners</p>
    </div>

    <div
      ref="card3"
      class="w-full sm:w-80 p-8 bg-[#F8FAFC]  rounded-lg shadow-md flex flex-col items-center justify-center text-center transition-all duration-300 hover:shadow-lg bg-dots"
    >
      <div class="md:text-5xl font-semibold text-gray-800 mb-2">
        {{ animatedNumber3.toLocaleString() }}k+
      </div>
      <p class="text-lg text-gray-600">Courses Completed</p>
    </div>
  </div>
  
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const animatedNumber1 = ref(0);
const animatedNumber2 = ref(0);
const animatedNumber3 = ref(0);

const targetNumber1 = 500; // Represents 500k
const targetNumber2 = 200; // Represents 200k
const targetNumber3 = 50;  // Represents 50k

const card1 = ref(null);
const card2 = ref(null);
const card3 = ref(null);

const observers = [];

const animateNumber = (refVar, target, duration = 2000) => {
  let start = null;
  const initialValue = refVar.value; // Get the current value to animate from

  const step = (timestamp) => {
    if (!start) start = timestamp;
    const progress = Math.min((timestamp - start) / duration, 1);
    refVar.value = Math.floor(initialValue + progress * (target - initialValue));

    if (progress < 1) {
      requestAnimationFrame(step);
    } else {
      refVar.value = target; // Ensure it ends exactly on the target
    }
  };
  requestAnimationFrame(step);
};

const setupObserver = (cardRef, animatedRef, targetNum) => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          animateNumber(animatedRef, targetNum);
          observer.unobserve(entry.target); // Unobserve once animated
        } else {
          // Optional: reset number when it scrolls out of view
          // animatedRef.value = 0; 
        }
      });
    },
    { threshold: 0.5 } // Trigger when 50% of the card is visible
  );

  if (cardRef.value) {
    observer.observe(cardRef.value);
    observers.push(observer);
  }
};

onMounted(() => {
  setupObserver(card1, animatedNumber1, targetNumber1);
  setupObserver(card2, animatedNumber2, targetNumber2);
  setupObserver(card3, animatedNumber3, targetNumber3);
});

onUnmounted(() => {
  observers.forEach(observer => observer.disconnect());
});
</script>

<style scoped>
.bg-dots {
  background-image: radial-gradient(#d1d5db 1px, transparent 1px); /* light gray dots */
  background-size: 8px 8px; /* Adjust dot size and spacing */
}
</style>