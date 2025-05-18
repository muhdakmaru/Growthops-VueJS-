<script setup>
import { ref, onMounted } from 'vue'

import CompanyViewRight from '@/components/CompanyViewRight.vue'
import CompanyViewLeft from '@/components/CompanyViewLeft.vue'
import companyImages from '@/data/CompanyImages.js'

const triggerRef = ref(null)
const startAnimation = ref(false)

onMounted(() => {
  const observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        startAnimation.value = true
        observer.disconnect()
      }
    },
    { threshold: 0.5 },
  )
  if (triggerRef.value) observer.observe(triggerRef.value)
})
</script>
<template>
  <div class="pb-40">
    <div class="">
      <div class="flex flex-row items-center justify-center w-full">
        <div
          class="relative max-w-[373px] sm:w-[373px] max-h-[110px] flex justify-center items-center"
        >
          <div
            class="absolute inset-0 border border-[#9747FF] rounded-[50%] z-20 pointer-events-none"
          ></div>
          <p
            class="ps-2 font-extrabold text-[40px] sm:text-[88px] gradient-text z-10 text-center px-2 gradient-super"
          >
            SUPER
          </p>
        </div>
        <span class="font-extrabold text-[40px] sm:text-[88px] text-center">PROUD</span>
        <p class="ml-5 hidden sm:block font-extrabold text-[40px] sm:text-[88px] text-center mr-2">
          TO
        </p>
      </div>
      <div
        class="relative w-full max-w-[920px] h-[18vw] max-h-[120px] mx-auto flex justify-center items-center -mt-4 sm:-mt-10"
      >
        <p class="block sm:hidden font-extrabold text-[40px] sm:text-[88px] text-center mr-2">TO</p>
        <p class="font-extrabold text-[40px] sm:text-[88px] text-center whitespace-nowrap">
          WORK WITH
        </p>
      </div>
    </div>

    <div class="pt-10 flex flex-row items-center justify-center max-w-[2000px] mx-auto">
      <div class="flex flex-col gap-y-8 overflow-hidden">
        <CompanyViewRight :images="companyImages.imageFirst" :start-animation="startAnimation" />
        <CompanyViewLeft :images="companyImages.imageSecond" :start-animation="startAnimation" />
        <CompanyViewRight :images="companyImages.imageThird" :start-animation="startAnimation" />
      </div>
    </div>

    <!-- Trigger Animation Dekat Sini -->
    <div ref="triggerRef"></div>

    <!-- Shadow Overlay -->
    <div class="relative flex flex-row justify-between">
      <div>
        <img
          src="@/assets/Images/shadow-overlay-left.svg"
          alt="Left Image"
          class="hidden sm:block absolute top-0 left-0 w-[250px] h-[400px] md:w-[350px] md:h-[600px] lg:w-[500px] lg:h-[900px] top-[-650px] z-50"
        />
        <img
          src="@/assets/Images/shadow-overlay-left-mobile.svg"
          alt="Left Image"
          class="sm:hidden absolute top-0 left-0 h-[350px] top-[-320px] z-50"
        />
      </div>
      <div>
        <img
          src="@/assets/Images/shadow-overlay-right.svg"
          alt="Right Image"
          class="hidden sm:block absolute top-0 right-0 w-[500px] h-[900px] top-[-650px] z-50"
        />
        <img
          src="@/assets/Images/shadow-overlay-right-mobile.svg"
          alt="Left Image"
          class="sm:hidden absolute top-0 right-0 h-[350px] top-[-320px] z-50"
        />
      </div>
    </div>

    <div class="flex flex-col items-center justify-center mt-60 sm:mt-80">
      <router-link to="/contact-us">
        <button
          class="cursor-pointer bg-[#33FF85] w-[177px] h-[54px] rounded-[48px] py-4 px-10 font-bold text-lg flex items-center justify-center transition-all duration-200 hover:bg-[#28cc6a] hover:shadow-lg"
        >
          Let's chat
        </button>
      </router-link>
    </div>
  </div>
</template>

<style scoped>
.gradient-super {
  background: linear-gradient(91.91deg, #9747ff 0.18%, #96bffd 32.82%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent;
}
</style>
