<script setup>
import { ref } from 'vue'

const active = ref('Telco')
const options = [
  {
    type: 'Telco',
    text: 'Through this initiative, GrowthOps have shown to have the right capabilities to take our platform to the next level. We believe the refreshed U.COM.MY will equip us with more insights, enabling us to make more data-led decisions that will result in new digital experiences that will truly benefit our customers.',
    reviewer: 'Jasmine Lee',
  },
  {
    type: 'Insurance',
    text: 'GrowthOps provided us with innovative solutions that streamlined our processes and improved customer satisfaction. Their expertise in digital transformation has enabled us to respond faster to market changes and deliver better value to our policyholders.',
    reviewer: 'Chee Hung Goon',
  },
  {
    type: 'Fintech',
    text: 'Partnering with GrowthOps accelerated our product development and enhanced our digital offerings. Their team brought fresh perspectives and technical excellence, helping us stay ahead in a rapidly evolving financial landscape.',
    reviewer: 'Shakira Pathmarajah ',
  },
  {
    type: 'IT',
    text: 'With GrowthOps, we successfully modernized our IT infrastructure and improved operational efficiency. Their collaborative approach and deep technical knowledge made a significant impact on our digital journey.',
    reviewer: 'Muhammad Akmal',
  },
]
</script>
<template>
  <div class="pb-100">
    <div class="flex justify-center items-center mb-5">
      <p
        class="font-extrabold text-[35px] sm:text-[88px] uppercase max-w-[300px] sm:max-w-full text-center"
      >
        what clients say
      </p>
    </div>
    <div class="flex justify-center items-center">
      <div class="w-[400px] h-[56px] border border-[#2B2B2B] rounded-full">
        <div class="flex justify-between items-center h-full px-2">
          <template v-for="option in options" :key="option">
            <button
              @click="active = option.type"
              :class="[
                'rounded-full w-[88px] h-[44px] flex justify-center items-center transition-colors duration-200 text-[16px] cursor-pointer',
                active === option.type
                  ? 'bg-[#07DDDA] text-black border border-[#07DDDA] font-bold'
                  : 'bg-transparent border border-transparent hover:bg-[#E0FDFD] hover:text-black hover:font-bold font-normal',
              ]"
            >
              <span>{{ option.type }}</span>
            </button>
          </template>
        </div>
      </div>
    </div>

    <div class="relative">
      <div class="flex flex-row justify-end">
        <img
          src="@/assets/Images/vector-3.svg"
          alt="Vector 3"
          class="absolute w-[800px] h-[1300px] sm:h-[1100px] top-[-300px] sm:top-[-250px] pointer-events-none"
        />
      </div>
    </div>

    <div class="flex flex-row justify-center items-center mt-15">
      <div class="w-[50px] h-[200px] flex flex-col justify-start items-center">
        <img src="@/assets/Images/text-symbol.svg" alt="text symbol" class="ms-2 mt-2" />
      </div>
      <div
        class="w-[600px] sm:w-[1000px] h-[200px] flex flex-col justify-start ps-5 sm:ps-15 mr-10 sm:mr-0"
      >
        <span class="font-medium text-[20px] sm:text-[24px] text-[#F5F5F5] mr-8">
          {{ options.find((opt) => opt.type === active)?.text }}
        </span>
        <div class="flex flex-col justify-start mt-10">
          <div class="mb-2">
            <span class="font-bold">{{
              options.find((opt) => opt.type === active)?.reviewer
            }}</span>
          </div>
          <div><span class="text-[#CCCCCC]">[Position], [Company Name]</span></div>
        </div>
      </div>
    </div>
  </div>
</template>
