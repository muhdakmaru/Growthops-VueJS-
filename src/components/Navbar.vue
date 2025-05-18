<template>
  <div class="flex justify-center">
    <div
      :class="[
        'bg-black border-2 rounded-[64px] w-[1800px] h-[69px] flex items-center justify-between px-4 sm:px-8 transition-colors duration-200',
        !showBorder ? 'flex border-[#F5F5F514]' : 'flex border-transparent',
      ]"
    >
      <div>
        <router-link to="/">
          <img
            src="@/assets/Icon/growthops-icon.png"
            alt="Icon"
            width="40"
            height="40"
            class="transition-opacity duration-200 hover:opacity-80"
          />
        </router-link>
      </div>
      <div>
        <button @click="openMenu" class="flex items-center cursor-pointer">
          <transition name="fade" mode="out-in">
            <div class="cursor-pointer hover:opacity-80">
              <span v-if="!showBorder" key="menu" class="flex items-center">
                <span
                  class="font-bold text-[14px] leading-[100%] tracking-normal text-right uppercase text-[#F5F5F5] pe-2 hidden sm:inline"
                >
                  Menu
                </span>
                <img
                  src="@/assets/Icon/button-icon.png"
                  alt="Icon"
                  width="40"
                  height="40"
                  class="transition-opacity duration-300"
                />
              </span>
              <span v-else key="close" class="flex items-center">
                <span
                  class="font-bold text-[14px] leading-[100%] tracking-normal text-right uppercase text-[#F5F5F5] pe-2 hidden sm:inline"
                >
                  Close
                </span>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  fill="currentColor"
                  class="size-6 transition-opacity duration-300"
                >
                  <path
                    fill-rule="evenodd"
                    d="M5.47 5.47a.75.75 0 0 1 1.06 0L12 10.94l5.47-5.47a.75.75 0 1 1 1.06 1.06L13.06 12l5.47 5.47a.75.75 0 1 1-1.06 1.06L12 13.06l-5.47 5.47a.75.75 0 0 1-1.06-1.06L10.94 12 5.47 6.53a.75.75 0 0 1 0-1.06Z"
                    clip-rule="evenodd"
                  />
                </svg>
              </span>
            </div>
          </transition>
        </button>
      </div>
    </div>
  </div>

  <div v-if="showBorder">
    <div class="justify-end sm:pe-16 md:pe-20 grid gap-4 text-end w-full p-4 sm:p-6">
      <router-link to="/services">
        <span
          class="font-extrabold text-[55px] sm:text-[45px] md:text-[45px] lg:text-[45px] xl:text-[65px] uppercase cursor-pointer hover:opacity-80"
          >Services</span
        >
      </router-link>
      <router-link to="/work">
        <span
          class="font-extrabold text-[55px] sm:text-[45px] md:text-[45px] lg:text-[45px] xl:text-[65px] uppercase cursor-pointer hover:opacity-80"
          >Work</span
        >
      </router-link>
      <router-link to="/inisights">
        <span
          class="font-extrabold text-[55px] sm:text-[45px] md:text-[45px] lg:text-[45px] xl:text-[65px] uppercase cursor-pointer hover:opacity-80"
          >Insights</span
        >
      </router-link>
      <router-link to="/careers">
        <span
          class="font-extrabold text-[55px] sm:text-[45px] md:text-[45px] lg:text-[45px] xl:text-[65px] uppercase cursor-pointer hover:opacity-80"
          >Careers</span
        >
      </router-link>
      <router-link to="/contact-us">
        <span
          class="font-extrabold text-[55px] sm:text-[45px] md:text-[45px] lg:text-[45px] xl:text-[65px] uppercase cursor-pointer hover:opacity-80"
          >Contact</span
        >
      </router-link>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const emit = defineEmits(['update:showBorder'])
const showBorder = ref(false)

function openMenu() {
  showBorder.value = !showBorder.value
  emit('update:showBorder', showBorder.value)
  console.log('Menu opened')
}
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.1s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0.5;
}
.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}
</style>
