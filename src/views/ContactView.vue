<script setup lang="ts">
import { onMounted, ref } from 'vue'
import Navbar from '@/components/Navbar.vue'
import ContactForm from '@/components/Layout/ContactForm.vue'
import OfficeLocation from '@/components/Layout/OfficeLocation.vue'
import Footer from '@/components/Layout/Footer.vue'

const showBorder = ref(false)

function handleShowBorder(val: boolean) {
  showBorder.value = val
  console.log('showBorder in Layout1:', val)
}
</script>
<template>
  <div class="">
    <div class="absolute top-0 left-1/2 -translate-x-1/2 z-50 p-4 w-full">
      <Navbar @update:showBorder="handleShowBorder" />
    </div>
  </div>

  <div
    v-if="showBorder"
    class="absolute left-0 right-0 top-0 h-[720px] sm:h-[760px] z-40 backdrop-blur-xs"
    style="pointer-events: none"
  ></div>

  <!-- Main Content Body -->
  <div>
    <div class="pt-10 pb-40">
      <ContactForm />
    </div>

    <div class="pb-10">
      <OfficeLocation />
    </div>
  </div>

  <!-- Footer -->
  <div>
    <Footer :redline="true" />
  </div>
</template>

<style></style>
