<script setup>
import AnimatedNumber from '@/components/AnimatedNumber.vue'
import { ref, onMounted } from 'vue'

// Bar 1 (30%)
const barWidth30 = ref(0)
const barRef30 = ref(null)
const hasAnimatedBar30 = ref(false)
function animateBar30(targetPercent = 30, duration = 1000) {
  const start = 0
  const end = targetPercent
  const frameRate = 1000 / 60
  const totalFrames = Math.round(duration / frameRate)
  let frame = 0
  const interval = setInterval(() => {
    frame++
    barWidth30.value = ((end - start) * frame) / totalFrames
    if (frame >= totalFrames) {
      barWidth30.value = end
      clearInterval(interval)
    }
  }, frameRate)
}

// Bar 2 (5%)
const barWidth5 = ref(0)
const barRef5 = ref(null)
const hasAnimatedBar5 = ref(false)
function animateBar5(targetPercent = 5, duration = 1000) {
  const start = 0
  const end = targetPercent
  const frameRate = 1000 / 60
  const totalFrames = Math.round(duration / frameRate)
  let frame = 0
  const interval = setInterval(() => {
    frame++
    barWidth5.value = ((end - start) * frame) / totalFrames
    if (frame >= totalFrames) {
      barWidth5.value = end
      clearInterval(interval)
    }
  }, frameRate)
}

onMounted(() => {
  // Bar 1 observer
  const observer30 = new window.IntersectionObserver(
    (entries) => {
      if (entries[0].isIntersecting && !hasAnimatedBar30.value) {
        hasAnimatedBar30.value = true
        animateBar30()
        observer30.disconnect()
      }
    },
    { threshold: 0.3 },
  )
  if (barRef30.value) {
    observer30.observe(barRef30.value)
  }

  // Bar 2 observer
  const observer5 = new window.IntersectionObserver(
    (entries) => {
      if (entries[0].isIntersecting && !hasAnimatedBar5.value) {
        hasAnimatedBar5.value = true
        animateBar5()
        observer5.disconnect()
      }
    },
    { threshold: 0.3 },
  )
  if (barRef5.value) {
    observer5.observe(barRef5.value)
  }
})
</script>
<template>
  <div>
    <!-- Unforgivable Results Text  -->
    <div class="p-2 sm:p-0">
      <div
        class="relative w-full max-w-[920px] max-h-[120px] mx-auto flex justify-center items-center"
      >
        <div
          class="absolute inset-0 border border-[#07ddda] rounded-[50%] z-20 pointer-events-none"
        ></div>
        <p class="font-extrabold text-[40px] sm:text-[88px] gradient-text z-10 text-center px-2">
          UNFORGETTABLE
        </p>
      </div>
      <div
        class="relative w-full max-w-[920px] h-[18vw] max-h-[120px] mx-auto flex justify-center items-center -mt-4 sm:-mt-6"
      >
        <p class="font-extrabold text-[40px] sm:text-[88px] text-center">RESULTS</p>
      </div>
    </div>
  </div>

  <!--  Results Information -->
  <div class="">
    <!-- First Column -->
    <div
      class="flex flex-col sm:flex-row justify-between p-5 max-w-[1000px] mx-auto"
      ref="numberSection"
    >
      <!-- Blue Box -->
      <div class="w-full sm:w-1/2 flex flex-col justify-start items-start">
        <div class="flex flex-col max-w-[250px] sm:max-w-[350px]">
          <AnimatedNumber
            :value="400"
            :duration="1500"
            customClass="text-[36px] sm:text-[64px] text-[#07DDDA] font-bold tracking-normal mb-2"
            suffix="%"
          />
          <span class="text-[14px] text-[#07DDDA] font-semibold mb-2 -mt-2 uppercase"
            >increase in organic page views</span
          >
          <span class="font-normal text-[14px] text-[#B4B4B4]"
            >Using our SEO services, it also resulted in a
            <b>109% increase in page visibility</b></span
          >
        </div>
      </div>
      <!-- Red Box -->
      <div class="w-full sm:w-1/2 flex flex-col justify-center items-center pt-10 sm:pt-20 ps-25">
        <div class="flex flex-col max-w-[400px]">
          <AnimatedNumber
            :value="4.5"
            :duration="1500"
            :decimals="1"
            customClass="text-[36px] sm:text-[64px] text-[#07DDDA] font-bold tracking-normal mb-2"
            suffix="%"
          />
          <span class="text-[14px] text-[#07DDDA] font-semibold mb-2 -mt-2 uppercase"
            >increase in sales</span
          >
          <span class="font-normal text-[14px] text-[#B4B4B4]"
            >Through our creative services, a national automaker experienced a
            <b>4.5% increase in sales amidst a -4.6% market decline.</b> They also had a
            <b>2% increase in market share</b>, and a
            <b>5.6 point shift in brand perception</b></span
          >
        </div>
      </div>
    </div>

    <!-- Second Column -->
    <div class="flex flex-col sm:flex-row justify-between p-5 max-w-[1000px] mx-auto">
      <!-- Blue Box -->
      <div class="w-full sm:w-1/2 flex flex-col justify-start items-start">
        <div class="flex flex-col max-w-[250px] sm:max-w-[350px]">
          <AnimatedNumber
            :value="96"
            :duration="1500"
            customClass="text-[36px] sm:text-[64px] text-[#07DDDA] font-bold tracking-normal mb-2"
            suffix="%"
          />
          <span class="text-[14px] text-[#07DDDA] font-semibold mb-2 -mt-2 uppercase"
            >faster page launches</span
          >
          <span class="font-normal text-[14px] text-[#B4B4B4]"
            >Using AEM, a leading Telco saw these results</span
          >
          <!-- Divider Box 30% -->
          <div class="mt-4">
            <div
              ref="barRef30"
              class="relative w-[277px] h-[40px] rounded-[4px] overflow-hidden mb-2"
            >
              <!-- Faded background bar -->
              <div class="absolute inset-0 bg-[#07DDDA] opacity-20"></div>
              <!-- Animated healthbar -->
              <div
                class="absolute left-0 top-0 h-full bg-[#07DDDA] opacity-100 rounded-[4px] transition-all duration-200"
                :style="{ width: barWidth30 + '%' }"
              ></div>
            </div>
            <span class="font-normal text-[14px] text-[#B4B4B4]">
              Campaign launches cut from <b>7 days to 2 days</b>
            </span>
          </div>

          <!-- Divider Box 5% -->
          <div class="mt-4">
            <div
              ref="barRef5"
              class="relative w-[277px] h-[40px] rounded-[4px] overflow-hidden mb-2"
            >
              <!-- Faded background bar -->
              <div class="absolute inset-0 bg-[#07DDDA] opacity-20"></div>
              <!-- Animated healthbar -->
              <div
                class="absolute left-0 top-0 h-full bg-[#07DDDA] opacity-100 rounded-[4px] transition-all duration-200"
                :style="{ width: barWidth5 + '%' }"
              ></div>
            </div>
            <span class="font-normal text-[14px] text-[#B4B4B4]">
              Page launches cut from <b>2 days to 2 hours</b>
            </span>
          </div>
        </div>
      </div>
      <!-- Red Box -->
      <div
        class="w-full sm:w-1/2 flex flex-col justify-center items-center pt-10 sm:pt-20 sm:pt-45 ps-25"
      >
        <div class="flex flex-col max-w-[400px]">
          <AnimatedNumber
            :value="71"
            :duration="1500"
            customClass="text-[36px] sm:text-[64px] text-[#07DDDA] font-bold tracking-normal mb-2"
            suffix="%"
          />
          <span class="text-[14px] text-[#07DDDA] font-semibold mb-2 -mt-2 uppercase"
            >Reduction in cpl</span
          >
          <span class="font-normal text-[14px] text-[#B4B4B4]"
            >After optimising the performance media funnel, a leading bank saw
            <b>savings over AUD$300 in the first year</b></span
          >
        </div>
      </div>
    </div>

    <!-- Third Column -->
    <div class="flex flex-col sm:flex-row justify-between p-5 max-w-[1000px] mx-auto">
      <!-- Blue Box -->
      <div class="w-full sm:w-1/2 flex flex-col justify-start items-start">
        <div class="flex flex-col max-w-[250px] sm:max-w-[350px]">
          <AnimatedNumber
            :value="38"
            :duration="1500"
            customClass="text-[36px] sm:text-[64px] text-[#07DDDA] font-bold tracking-normal mb-2"
            suffix="%"
          />
          <span class="text-[14px] text-[#07DDDA] font-semibold mb-2 -mt-2 uppercase"
            >conversion rate improvement</span
          >
          <span class="font-normal text-[14px] text-[#B4B4B4]"
            >Using Adobe Target to A/B test landing pages’ forms, we saw an
            <b>increase in conversion rate</b></span
          >
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.gradient-text {
  background: linear-gradient(
    90.54deg,
    rgb(0, 76, 186) 0.06%,
    rgb(25, 178, 167) 44.49%,
    rgb(253, 209, 150) 83.69%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent;
}
</style>
