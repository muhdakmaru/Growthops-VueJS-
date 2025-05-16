<script setup>
import businessSections from '@/data/businessData'
</script>
<template>
  <div>
    <div class="flex justify-center items-center mb-5">
      <p class="font-extrabold text-[35px] sm:text-[88px] whitespace-nowrap">WHAT WE DO</p>
    </div>
    <div class="p-12 sm:p-15">
      <div
        v-for="(section, idx) in businessSections"
        :key="idx"
        class="flex flex-col sm:flex-row justify-center items-center mb-20"
      >
        <!-- Even: Info left, image right | Odd: Image left, info right -->
        <template v-if="idx % 2 === 0">
          <!-- Info -->
          <div
            class="order-2 sm:order-1 flex flex-col justify-start items-start w-full sm:w-auto p-0 sm:p-15"
          >
            <img
              :src="section.icon"
              alt="Business Page"
              class="object-contain max-w-full max-h-full mb-5"
            />
            <div
              class="font-extrabold text-[24px] sm:text-[40px] text-[#F5F5F5] mb-4 max-w-full sm:max-w-[400px]"
            >
              {{ section.title }}
            </div>
            <div class="flex-row mt-4 space-y-4 mb-8 max-w-full sm:max-w-[400px]">
              <p
                v-for="(item, i) in section.items"
                :key="i"
                class="font-normal text-[16px] sm:text-[20px] text-[#CCCCCC]"
              >
                {{ item }}
              </p>
            </div>
            <button
              class="rounded-full border p-2 w-35 cursor-pointer transition-colors duration-200 hover:bg-[#F5F5F5] hover:text-black hover:border-[#F5F5F5]"
            >
              <span class="font-extrabold">See More</span>
            </button>
          </div>
          <!-- Image -->
          <div class="order-1 sm:order-2 flex justify-center mb-4 sm:mb-0 sm:ml-8">
            <img
              :src="section.image"
              alt="Business Page"
              class="object-contain max-w-full max-h-full sm:w-[980px] sm:h-[700px]"
            />
          </div>
        </template>
        <template v-else>
          <!-- Image -->
          <div class="order-1 sm:order-1 flex justify-center mb-4 sm:mb-0 sm:mr-8">
            <img
              :src="section.image"
              alt="Business Page"
              class="object-contain max-w-full max-h-full sm:w-[980px] sm:h-[700px]"
            />
          </div>
          <!-- Info -->
          <div
            class="order-2 sm:order-2 flex flex-col justify-start items-start w-full sm:w-auto p-0 sm:p-15"
          >
            <img
              :src="section.icon"
              alt="Business Page"
              class="object-contain max-w-full max-h-full mb-5"
            />
            <div
              class="font-extrabold text-[24px] sm:text-[40px] text-[#F5F5F5] mb-4 max-w-full sm:max-w-[400px]"
            >
              {{ section.title }}
            </div>
            <div class="flex-row mt-4 space-y-4 mb-8 max-w-full sm:max-w-[400px]">
              <p
                v-for="(item, i) in section.items"
                :key="i"
                class="font-normal text-[16px] sm:text-[20px] text-[#CCCCCC]"
              >
                {{ item }}
              </p>
            </div>
            <button
              class="rounded-full border p-2 w-35 cursor-pointer transition-colors duration-200 hover:bg-[#F5F5F5] hover:text-black hover:border-[#F5F5F5]"
            >
              <span class="font-extrabold">See More</span>
            </button>
          </div>
        </template>
      </div>
    </div>
  </div>
</template>
