<script setup>
import VideoSection from '@/components/Navbars/pages/VideoSection.vue';
import Dropdown from './components/Navbars/Dropdown.vue';
import FloatingAnimated from './components/Navbars/FloatingAnimated.vue';
import GlassBar from './components/Navbars/GlassBar.vue';
import LiquidWave from './components/Navbars/LiquidWave.vue';
import Mobile from './components/Navbars/Mobile.vue';
import Benefits from './components/Navbars/pages/benefits.vue';
import Capabalities from './components/Navbars/pages/capabalities.vue';
import Carousel from './components/Navbars/pages/carousel.vue';
import ExperienceCard from './components/Navbars/pages/experienceCard.vue';
import Faqs from './components/Navbars/pages/Faqs.vue';
import Footer from './components/Navbars/pages/Footer.vue';
import GetStart from './components/Navbars/pages/getStart.vue';
import KeyFeatures from './components/Navbars/pages/keyFeatures.vue';
import PricingCards from './components/Navbars/pages/pricingCards.vue';
import Particle from './components/Navbars/particle.vue';
import ProfileBar from './components/Navbars/ProfileBar.vue';
import SearchBar from './components/Navbars/SearchBar.vue';
import Sidebar from './components/Navbars/Sidebar.vue';
import navbar from '@/components/Navbars/pages/navbar.vue'
import SocailMedia from '@/components/Navbars/pages/SocailMedia.vue'
import Services from '@/components/Navbars/pages/Services.vue'
import ImportantLinks from '@/components/Navbars/pages/ImportantLinks.vue'
import Form from './components/Navbars/pages/form.vue';
import Globe from './components/Navbars/pages/globe.vue';


</script>
<template>
<!-- <Dropdown/>
<!-- <GlassBar/> -->
<!-- <Mobile/> -->
<!-- <ProfileBar/> -->
<!-- <SearchBar/> -->
<!-- <Sidebar/> -->
     <!-- <FloatingAnimated/> -->
     <!-- <LiquidWave/> -->
     <!-- <Particle/> -->
     
     <navbar />
     <SocailMedia/>
     <div class="bg-dots bg-[#fcfbff] pb-10">
     
     <div class="w-full px-4 max-w-5xl mx-auto ">
     <VideoSection 
     class=""
      animation-style="from-center"
      video-src="/src/assets/vid.webm"
      thumbnail-src="/src/assets/thumb.png"
      thumbnail-alt="Hero Video"
      />
     </div>
     </div>
     
     <ExperienceCard/>
     <Benefits/>   
     <!-- <KeyFeatures/> -->
     <!-- <Capabalities/> -->
     <!-- <GetStart/> -->
     <PricingCards/>
     <Carousel/>
     <Faqs/>
    <div class="relative min-h-screen  flex flex-col lg:flex-row items-center justify-center bg-[#F8F9FA] p-4 sm:p-8">
    <div class="w-full lg:w-1/2 h-96 lg:h-screen-75 flex justify-center items-center mb-8 lg:mb-0 lg:mr-8">
      <Globe />
    </div>

    <div class="w-full lg:w-1/2 flex justify-center items-center">
      <Form />
    </div>
  </div>
     <Services/>
     <!-- <ImportantLinks/> -->
     <Footer/>
</template>
    