<script setup lang="ts">
import Navbar from '@/components/Navbar.vue'
import LandingPage from '@/components/Layout/LandingPage.vue'
import Growthops from '@/components/Layout/Growthops.vue'
import BusinessPage from '@/components/Layout/BusinessPage.vue'
import Results from '@/components/Layout/Results.vue'
import ClientReview from '@/components/Layout/ClientReview.vue'
import Company from '@/components/Layout/Company.vue'
import Footer from '@/components/Layout/Footer.vue'

import { onMounted, ref, watch } from 'vue'
import { useRouter } from 'vue-router'

const show = ref(true)
const showMain = ref(false)
const router = useRouter()

const showBorder = ref(false)

function handleShowBorder(val: boolean) {
  showBorder.value = val
}

onMounted(() => {
  setTimeout(() => {
    show.value = false
    showMain.value = true
    setTimeout(() => {
      // showMain.value = true
      // router.push({ name: 'home' }) // Remove or delay this if you want to show LandingPage
    }, 1500)
  }, 2000)
})

watch(show, (val) => {
  document.body.style.overflow = val ? 'hidden' : ''
})
</script>

<template>
  <!--  NavBar & Blur Effet  -->
  <div class="relative">
    <div class="absolute top-0 left-1/2 -translate-x-1/2 z-50 p-3 sm:p-6 w-full pt-2 sm:pt-5">
      <Navbar @update:showBorder="handleShowBorder" :contactPage="false" />
    </div>
  </div>

  <div
    v-if="showBorder"
    class="absolute left-0 right-0 top-0 h-[720px] sm:h-[800px] z-40 backdrop-blur-md"
    style="pointer-events: none"
  ></div>

  <div>
    <!--  Growthops Transition  -->
    <transition name="slideout-bottom" appear mode="out-in">
      <div v-if="show" class="fixed inset-0 flex items-center justify-center bg-white z-[9999]">
        <img
          src="@/assets/Images/page-slide.png"
          alt="Welcome"
          class="hidden sm:block w-full h-full object-cover"
        />

        <img
          src="@/assets/Images/mobile-slide.png"
          alt="Welcome"
          class="block sm:hidden w-full h-full object-cover"
        />
      </div>
    </transition>

    <!-- Landing Page need to fix Text Absolute class then can use the transition -->
    <transition name="slidein-bottom" appear>
      <div v-if="showMain">
        <LandingPage />
      </div>
    </transition>

    <!-- Main Page Header -->
    <!-- <header class="pb-10 sm:pb-20">
      <LandingPage />
    </header> -->

    <!-- Main Page Body -->
    <div>
      <div class="pt-30 pb-50 hidden sm:block">
        <Growthops class="" />
      </div>

      <div class="pb-10 sm:pb-35 pt-10 sm:pt-0">
        <BusinessPage />
      </div>

      <div class="block sm:hidden pb-60">
        <Growthops />
      </div>

      <div class="pb-30">
        <Results />
      </div>

      <div class="pb-20">
        <ClientReview />
      </div>

      <div class="pb-20">
        <Company />
      </div>
    </div>

    <!-- Main Page Footer -->
    <div>
      <Footer />
    </div>
  </div>
</template>

<style scoped>
.slideout-bottom-leave-active {
  transition:
    transform 1.5s linear,
    opacity 1.5s linear;
}
.slideout-bottom-leave-to {
  transform: translateY(-100vh); /* Slide up (bottom to top) */
  opacity: 1;
}

/* Slide in from bottom for main page */
.slidein-bottom-enter-active {
  transition:
    transform 1.5s linear,
    opacity 1s;
}
.slidein-bottom-enter-from {
  transform: translateY(300px);
  opacity: 1;
}
.slidein-bottom-enter-to {
  transform: translateY(0);
  opacity: 1;
}
</style>
