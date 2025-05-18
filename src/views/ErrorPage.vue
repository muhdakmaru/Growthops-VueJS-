<script setup>
import Navbar from '@/components/Navbar.vue'
</script>
<template>
  <div class="flex flex-col items-center justify-center min-h-screen text-center w-full">
    <h1 class="text-6xl font-extrabold mb-4">404</h1>
    <p class="text-xl mb-6 font-semibold">Page Not Found</p>
    <router-link
      to="/"
      class="text-white mb-8 font-medium transition-opacity duration-200 hover:opacity-80"
    >
      <span>Go Home</span>
    </router-link>
    <hr
      class="w-screen border-t-2 border border-[#FFFBFC] my-3 line-wave"
      style="animation-delay: 1.5s"
    />

    <hr
      class="w-screen border-t-2 border border-[#FF3366] my-3 line-wave"
      style="animation-delay: 1s"
    />
    <hr
      class="w-screen border-t-2 border border-[#FFFBFC] my-3 line-wave"
      style="animation-delay: 2s"
    />
    <hr
      class="w-screen border-t-2 border border-[#FF3366] my-3 line-wave"
      style="animation-delay: 0.5s"
    />
  </div>
</template>

<style>
.line-wave {
  border-width: 1px;
  pointer-events: none;
  opacity: 100%;
  animation: waveOpacity 2.5s ease-in-out infinite;
}

@keyframes waveOpacity {
  0% {
    opacity: 0.2;
  }
  25% {
    opacity: 1;
  }
  50% {
    opacity: 1;
  }
  75% {
    opacity: 0.4;
  }
  100% {
    opacity: 0.2;
  }
}
</style>
