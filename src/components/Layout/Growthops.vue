<template>
  <div>
    <!-- Style Image Vector -->
    <div class="relative flex justify-start items-start">
      <div>
        <!-- Vector Desktop Image -->
        <img
          src="@/assets/Images/vector-1.svg"
          alt="Landing Page"
          class="hidden sm:absolute sm:block w-[800px] h-[1200px] top-[-180px]"
        />
        <!-- Vector Mobile Image -->
        <img
          src="@/assets/Images/vector-1.svg"
          alt="Landing Page"
          class="absolute w-[800px] h-[1200px] top-[-400px] right-[90px] block sm:hidden"
        />
      </div>
    </div>
    <div
      class="relative flex flex-col items-center text-center gap-14 text-[32px] max-w-3xl mx-auto pt-10"
    >
      <div>
        <img src="@/assets/Images/landing-text.svg" alt="Icon" class="hidden sm:block" />
        <img src="@/assets/Images/landing-text-mobile.svg" alt="Icon" class="block sm:hidden" />
      </div>
      <div class="text-[20px] sm:text-[32px]">
        <span>this is</span>
      </div>
      <div class="">
        <p
          class="font-extrabold text-[36px] sm:text-[96px] leading-[100%] tracking-[-0.01em] text-center whitespace-nowrap bg-gradient-to-r from-[#33FFF3] via-[#FF33F6] via-[#FFD633] via-[#33FF57] via-[#335BFF] to-[#98E0FF] bg-clip-text text-transparent animate-rgb-gradient"
        >
          GrowthOps Asia
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes rgb-gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
.animate-rgb-gradient {
  background-size: 200% 200%;
  animation: rgb-gradient 3s ease-in-out infinite;
}
</style>
