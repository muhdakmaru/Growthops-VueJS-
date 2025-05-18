<script setup lang="ts">
defineProps<{ redline: boolean; contactPage: boolean }>()
</script>
<template>
  <div class="">
    <!--  Footer Circles  -->
    <!--   Desktop Circle    -->
    <div class="hidden sm:flex flex-row justify-center item-center h-[450px] overflow-hidden">
      <div v-if="!redline" class="relative">
        <div
          class="relative rounded-full border"
          :style="{
            width: '4980px',
            height: '4980px',
            borderColor: 'rgba(243, 243, 243, 0.3)',
          }"
        >
          <div
            class="absolute rounded-full border top-0 left-0 right-0 bottom-0 m-auto"
            :style="{
              width: '4750px',
              height: '4750px',
              borderColor: 'rgba(243, 232, 255, 0.5)',
            }"
          >
            <div
              class="absolute rounded-full border top-0 left-0 right-0 bottom-0 m-auto"
              :style="{
                width: '4600px',
                height: '4600px',
                borderColor: 'rgba(233, 213, 255, 0.7)',
              }"
            ></div>
          </div>
        </div>
      </div>

      <div v-else class="relative">
        <div
          class="relative rounded-full border"
          :style="{
            width: '4980px',
            height: '4980px',
            borderColor: 'rgba(255, 51, 102, 0.3)',
          }"
        >
          <div
            class="absolute rounded-full border top-0 left-0 right-0 bottom-0 m-auto"
            :style="{
              width: '4750px',
              height: '4750px',
              borderColor: 'rgba(243, 232, 255, 0.5)',
            }"
          >
            <div
              class="absolute rounded-full border top-0 left-0 right-0 bottom-0 m-auto"
              :style="{
                width: '4600px',
                height: '4600px',
                borderColor: 'rgba(233, 213, 255, 0.7)',
              }"
            ></div>
          </div>
        </div>
      </div>
    </div>

    <!--   Mobile Circle    -->
    <div class="flex flex-row justify-center item-center h-[200px] overflow-hidden sm:hidden">
      <div class="relative">
        <div
          class="relative rounded-full border"
          :style="{
            width: '1000px',
            height: '1000px',
            borderColor: 'rgba(255, 51, 102, 0.3)',
          }"
        >
          <div
            class="absolute rounded-full border top-0 left-0 right-0 bottom-0 m-auto"
            :style="{
              width: '870px',
              height: '870px',
              borderColor: 'rgba(243, 232, 255, 0.5)',
            }"
          >
            <div
              class="absolute rounded-full border top-0 left-0 right-0 bottom-0 m-auto"
              :style="{
                width: '740px',
                height: '740px',
                borderColor: 'rgba(243, 232, 255, 0.7)',
              }"
            ></div>
          </div>
        </div>
      </div>
    </div>

    <div v-if="contactPage">
      <div class="flex flex-col justify-start items-start gap-4 p-8 text-[16px]">
        <div>
          <span class="text-[14px] font-semibold uppercase text-[#666666]">Asia</span>
        </div>
        <div class="flex flex-col justify-start items-start gap-3 font-normal text-[#F5F5F5]">
          <span>Hong Kong</span>
          <span>Kuala Lumpur</span>
          <span>Manila</span>
          <span>Singapore</span>
        </div>

        <div>
          <span class="text-[14px] font-semibold uppercase text-[#666666]">Middle East</span>
        </div>
        <div
          class="text-[16px] flex flex-col justify-start items-start gap-3 font-normal text-[#F5F5F5]"
        >
          <span>United Arab Emirates</span>
        </div>
      </div>
    </div>

    <!--  Footer Buttons  -->
    <div
      v-if="!contactPage"
      class="flex flex-wrap items-center justify-center gap-x-13 gap-y-6 pb-10"
    >
      <button class="cursor-pointer text-white hover:opacity-80">Services</button>
      <button class="cursor-pointer text-white hover:opacity-80">Works</button>
      <button class="cursor-pointer text-white hover:opacity-80">Insights</button>
      <button class="cursor-pointer text-white hover:opacity-80">Careers</button>
      <button class="cursor-pointer text-white hover:opacity-80">Contact Us</button>
    </div>

    <div class="flex flex-wrap items-center justify-center gap-x-12 sm:gap-x-18 gap-y-6">
      <a
        href="https://www.linkedin.com/company/growthops-asia/"
        target="_blank"
        rel="noopener noreferrer"
      >
        <img
          src="@/assets/Icon/linkedin.svg"
          alt="LinkedIn"
          class="cursor-pointer hover:opacity-80 w-[40px] h-[40px] sm:w-[32px] sm:h-[32px]"
        />
      </a>
      <a href="https://www.facebook.com/growthopsasia/" target="_blank" rel="noopener noreferrer">
        <img
          src="@/assets/Icon/facebook.svg"
          alt="Facebook"
          class="cursor-pointer hover:opacity-80 w-[40px] h-[40px] sm:w-[32px] sm:h-[32px]"
        />
      </a>
      <a
        href="https://www.instagram.com/growthopsasia/?hl=en"
        target="_blank"
        rel="noopener noreferrer"
      >
        <img
          src="@/assets/Icon/instagram.svg"
          alt="Instagram"
          class="cursor-pointer hover:opacity-80 w-[40px] h-[40px] sm:w-[32px] sm:h-[32px]"
        />
      </a>
      <a href="https://www.youtube.com/@growthopsasia" target="_blank" rel="noopener noreferrer">
        <img
          src="@/assets/Icon/youtube.svg"
          alt="YouTube"
          class="cursor-pointer hover:opacity-80 w-[40px] h-[40px] sm:w-[32px] sm:h-[32px]"
        />
      </a>
    </div>

    <!-- Blank Bottom Padding -->
    <div class="pb-6" v-if="contactPage"></div>

    <div v-if="!contactPage" class="pb-0 sm:pb-10">
      <div class="flex flex-row item-center justify-center sm:justify-between p-10 pt-15">
        <div class="hidden sm:block">
          <p class="font-semibold text-[12px] text-[#6F7176] uppercase">
            © Copyright GrowthOps. All rights reserved.
          </p>
        </div>
        <div
          class="flex flex-col sm:flex-row items-center justify-center sm:justify-between gap-4 sm:gap-10"
        >
          <div class="">
            <a href="https://www.growthops.asia/" target="_blank" rel="noopener noreferrer">
              <p
                class="flex items-center font-medium text-[12px] text-[#F5F5F5] cursor-pointer hover:opacity-80 whitespace-nowrap"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="inline-block mr-1"
                  width="16"
                  height="16"
                  fill="currentColor"
                  viewBox="0 0 512 512"
                >
                  <path
                    d="M432 320a16 16 0 0 1 16 16v112a48 48 0 0 1-48 48H80a48 48 0 0 1-48-48V112a48 48 0 0 1 48-48h112a16 16 0 0 1 0 32H80a16 16 0 0 0-16 16v336a16 16 0 0 0 16 16h320a16 16 0 0 0 16-16V336a16 16 0 0 1 16-16zm56-304H320a24 24 0 0 0-17 41l35 35-215 215a24 24 0 0 0 0 34l23 23a24 24 0 0 0 34 0l215-215 35 35a24 24 0 0 0 41-17V40a24 24 0 0 0-24-24z"
                  />
                </svg>
                Go to global GrowthOps website
              </p>
            </a>
          </div>
          <div>
            <a
              href="https://www.growthops.asia/privacy-policy"
              target="_blank"
              rel="noopener noreferrer"
            >
              <p class="font-medium text-[12px] text-[#F5F5F5] cursor-pointer hover:opacity-80">
                Privacy policy
              </p>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
