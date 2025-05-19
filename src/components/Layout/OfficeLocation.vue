<script setup>
import { offices } from '@/data/officeData'
import { ref, computed, onMounted, onUnmounted } from 'vue'

const isMobile = ref(false)

function checkMobile() {
  isMobile.value = window.innerWidth < 640 // Tailwind's sm breakpoint
}

onMounted(() => {
  checkMobile()
  window.addEventListener('resize', checkMobile)
})
onUnmounted(() => {
  window.removeEventListener('resize', checkMobile)
})

const reorderedOffices = computed(() => {
  if (!isMobile.value) return offices
  // Move the third office to the second position
  const arr = offices.slice()
  const third = arr.splice(2, 1)[0]
  arr.splice(1, 0, third)
  return arr
})
</script>

<template>
  <div>
    <div class="flex flex-row justify-center items-center">
      <span class="font-extrabold text-[35px] sm:text-[88px] whitespace-nowrap uppercase"
        >our offices</span
      >
    </div>

    <div class="flex justify-center items-center">
      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-12 p-6 justify-start items-center place-items-center"
      >
        <div
          v-for="office in reorderedOffices"
          :key="office.city"
          class="relative flex flex-col justify-start items-start max-w-full sm:max-w-[420px] max-h-full sm:h-[300px] border-2 border-[#F5F5F514] rounded-3xl gap-6 px-8 py-6 shadow-inner shadow-[inset_0_4px_24px_-1px_rgba(0,0,0,0.4)] backdrop-blur-[40px]"
        >
          <div class="flex flex-col justify-start items-start">
            <span
              class="font-semibold text-[12px] text-[#07DDDA] sm:text-[#B4B4B4] whitespace-nowrap uppercase"
              >{{ office.region }}</span
            >
            <span class="font-extrabold text-[24px] text-[#07DDDA] uppercase">
              {{ office.city }}
            </span>
          </div>
          <div class="flex flex-col justify-start items-start gap-4">
            <div v-if="office.phone" class="flex flex-row justify-start items-start gap-2">
              <img
                class="w-[24px] h-[24px] object-cover hidden sm:block"
                src="@/assets/Icon/phone-icon.svg"
                alt="phone"
              />
              <img
                class="w-[24px] h-[24px] object-cover block sm:hidden"
                src="@/assets/Icon/phone-icon-mobile.svg"
                alt="phone"
              />
              <span class="font-medium text-[16px] uppercase">{{ office.phone }}</span>
            </div>
            <div v-if="office.email" class="flex flex-row justify-start items-start gap-2">
              <img
                class="w-[24px] h-[24px] object-cover hidden sm:block"
                src="@/assets/Icon/email-icon.svg"
                alt="email"
              />
              <img
                class="w-[24px] h-[24px] object-cover block sm:hidden"
                src="@/assets/Icon/email-icon-mobile.svg"
                alt="email"
              />
              <span class="font-medium text-[16px]">{{ office.email }}</span>
            </div>
            <div class="flex flex-row justify-start items-start gap-2">
              <img
                class="w-[24px] h-[24px] object-cover hidden sm:block"
                src="@/assets/Icon/address-icon.svg"
                alt="address"
              />
              <img
                class="w-[24px] h-[24px] object-cover block sm:hidden"
                src="@/assets/Icon/address-icon-mobile.svg"
                alt="address"
              />
              <span class="font-medium text-[16px] break-words">{{ office.address }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div
      class="flex flex-row justify-start sm:justify-center ml-10 sm:ml-0 items-center pt-10 sm:pt-20"
    >
      <div class="">
        <div class="w-[200px] sm:w-full">
          <span class="hidden sm:block font-extrabold text-[35px] sm:text-[88px] uppercase block"
            >Keep in touch</span
          >
          <span class="font-extrabold text-[35px] sm:text-[88px] uppercase block sm:hidden"
            >Keep</span
          >
          <span class="font-extrabold text-[35px] sm:text-[88px] uppercase block sm:hidden"
            >In Touch</span
          >
        </div>
      </div>
    </div>
  </div>
</template>
