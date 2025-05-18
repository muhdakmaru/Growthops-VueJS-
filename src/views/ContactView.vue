<script setup lang="ts">
import { onMounted, ref } from 'vue'
import Navbar from '@/components/Navbar.vue'
import ContactForm from '@/components/Layout/ContactForm.vue'
import OfficeLocation from '@/components/Layout/OfficeLocation.vue'
import Footer from '@/components/Layout/Footer.vue'
import Testing from '@/components/Layout/testing.vue'

const showBorder = ref(false)

function handleShowBorder(val: boolean) {
  showBorder.value = val
  console.log('showBorder in Layout1:', val)
}
</script>
<template>
  <div class="relative">
    <div class="absolute top-0 left-1/2 -translate-x-1/2 z-50 p-4 w-full">
      <Navbar @update:showBorder="handleShowBorder" />
    </div>
  </div>

  <div
    v-if="showBorder"
    class="absolute left-0 right-0 top-0 h-[700px] sm:h-[800px] z-40 backdrop-blur-xs"
    style="pointer-events: none"
  ></div>

  <!-- Main Content Body -->
  <div>
    <div class="pt-10 sm:pt-5 pb-40">
      <ContactForm />
    </div>

    <div class="pb-10">
      <OfficeLocation />
    </div>
  </div>

  <!-- Footer -->
  <div>
    <Footer :redline="true" :contactPage="true" />
  </div>
</template>

<style></style>
