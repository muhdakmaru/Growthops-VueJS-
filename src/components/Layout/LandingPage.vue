<script></script>

<template>
  <!-- Background Circle Animation Web -->
  <!-- NEW CIRCLE IMPROVED  -->
  <div class="relative flex flex-row justify-center hidden sm:flex">
    <div class="relative max-h-[1600px]">
      <div
        class="relative mx-auto rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
        :style="{
          width: '2150px',
          height: '2150px',
          opacity: 0.1,
          top: '520px',
          animationDelay: '1.8s',
        }"
      ></div>
      <div class="relative">
        <div
          class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
          :style="{
            width: '1900px',
            height: '1900px',
            opacity: 0.2,
            top: '-1400px',
            animationDelay: '1.5s',
          }"
        ></div>
      </div>

      <div class="relative">
        <div
          class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
          :style="{
            width: '1600px',
            height: '1600px',
            opacity: 0.3,
            top: '-1700px',
            animationDelay: '1.2s',
          }"
        ></div>
      </div>

      <div class="relative">
        <div
          class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right- bottom-0 m-auto circle-wave"
          :style="{
            width: '1250px',
            height: '1250px',
            opacity: 0.4,
            top: '-2050px',
            animationDelay: '0.9s',
          }"
        ></div>
      </div>

      <div class="relative">
        <div
          class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
          :style="{
            width: '860px',
            height: '860px',
            opacity: 0.5,
            left: '870px',
            top: '-2450px',
            animationDelay: '0.3s',
          }"
        ></div>
      </div>

      <div class="relative">
        <div
          class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
          :style="{
            width: '520px',
            height: '520px',
            opacity: 0.7, // Lowest opacity
            left: '520px',
            top: '-2780px',
            animationDelay: '0.3s',
          }"
        ></div>
      </div>
    </div>
  </div>

  <!-- OLD CIRCLE -->
  <!-- <div class="flex justify-center w-full overflow-hidden hidden sm:inline">
    <div class="max-h-[1600px]">
      <div
        class="relative mx-auto rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
        :style="{
          width: '2150px',
          height: '2150px',
          opacity: 1,
          top: '520px', // Move the circle upwards to overlap the top of the page
          animationDelay: '1.5s',
        }"
      >
        <div
          class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
          :style="{
            width: '1900px',
            height: '1900px',
            opacity: 0.85,
            top: '1900px', // Move this circle down by 120px (adjust as needed)
            animationDelay: '1.2s',
          }"
        >
          <div
            class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
            :style="{
              width: '1600px',
              height: '1600px',
              opacity: 0.7,
              top: '1600px', // Move this circle down by 120px (adjust as needed)
              animationDelay: '0.9s',
            }"
          >
            <div
              class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
              :style="{
                width: '1250px',
                height: '1250px',
                opacity: 0.55,
                top: '1250px', // Move this circle down by 120px (adjust as needed)
                animationDelay: '0.6s',
              }"
            >
              <div
                class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
                :style="{
                  width: '880px',
                  height: '880px',
                  opacity: 0.4,
                  top: '880px',
                  animationDelay: '0.3s',
                }"
              >
                <div
                  class="absolute rounded-full border border-[#FFFBFC] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
                  :style="{
                    width: '480px',
                    height: '480px',
                    opacity: 0.25, // Lowest opacity
                    top: '480px',
                    animationDelay: '0s',
                  }"
                ></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div> -->

  <!-- Background Circle Animation Mobile -->
  <!-- NEW CIRCLE IMPROVED -->
  <div class="relative flex flex-row justify-center items-center sm:hidden">
    <div class="relative">
      <div
        class="relative mx-auto rounded-full border border-[#FF3366] top-0 left-0 right-0 bottom-0 m-auto circle-wave-mobile"
        :style="{
          width: '810px',
          height: '810px',
          opacity: 0.4,
          top: '395px',
          animationDelay: '1.8s',
        }"
      ></div>
    </div>

    <div class="relative">
      <div
        class="absolute rounded-full border border-[#FF3366] top-0 left-0 right-0 bottom-0 m-auto circle-wave-mobile"
        :style="{
          width: '685px',
          height: '685px',
          opacity: 0.5,
          left: '-410px',
          top: '330px',
          animationDelay: '1.5s',
        }"
      ></div>
    </div>

    <div class="relative">
      <div
        class="absolute rounded-full border border-[#FF3366] top-0 left-0 right-0 bottom-0 m-auto circle-wave-mobile"
        :style="{
          width: '570px',
          height: '570px',
          opacity: 0.6,
          left: '-410px',
          top: '260px',
          animationDelay: '1.2s',
        }"
      ></div>
    </div>

    <div class="relative">
      <div
        class="absolute rounded-full border border-[#FF3366] top-0 left-0 right-0 bottom-0 m-auto circle-wave-mobile"
        :style="{
          width: '460px',
          height: '460px',
          opacity: 0.9,
          left: '-408px',
          top: '203px',
          animationDelay: '0.9s',
        }"
      ></div>
    </div>
  </div>
  <!-- OLD CIRCLE-->
  <!-- <div class="flex justify-center w-full overflow-hidden sm:hidden">
    <div class="relative">
      <div
        class="relative mx-auto rounded-full border border-[#FF3366] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
        :style="{
          width: '1300px',
          height: '1300px',
          opacity: 1,
          top: '520px', // Move the circle upwards to overlap the top of the page
          animationDelay: '2.5s',
        }"
      >
        <div
          class="absolute rounded-full border border-[#FF3366] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
          :style="{
            width: '980px',
            height: '980px',
            opacity: 0.55,
            top: '1030px', // Move this circle down by 120px (adjust as needed)
            animationDelay: '0.6s',
          }"
        >
          <div
            class="absolute rounded-full border border-[#FF3366] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
            :style="{
              width: '760px',
              height: '760px',
              opacity: 0.4,
              top: '760px',
              animationDelay: '0.3s',
            }"
          >
            <div
              class="absolute rounded-full border border-[#FF3366] top-0 left-0 right-0 bottom-0 m-auto circle-wave"
              :style="{
                width: '550px',
                height: '550px',
                opacity: 0.25, // Lowest opacity
                top: '550px',
                animationDelay: '0.3s',
              }"
            ></div>
          </div>
        </div>
      </div>
    </div>
  </div> -->

  <div class="relative flex justify-center item-center">
    <div
      class="absolute inset-0 top-[-950px] sm:top-[-2250px] flex flex-col items-center justify-center gap-0 sm:gap-4 px-4 sm:px-0 ip-se"
      :style="{
        zIndex: 10,
        pointerEvents: 'none',
      }"
    >
      <div class="text-start mr-0 sm:mr-50 whitespace-nowrap">
        <span
          class="font-extrabold uppercase text-[32px] sm:text-5xl md:text-6xl lg:text-7xl xl:text-[98px]"
        >
          Your new-breed,
        </span>
      </div>
      <div class="text-end ml-32 sm:ml-160 whitespace-nowrap">
        <span
          class="font-extrabold uppercase text-[32px] sm:text-5xl md:text-6xl lg:text-7xl xl:text-[98px]"
        >
          end-to-end
        </span>
      </div>
      <div class="text-start mr-25 sm:mr-70 whitespace-nowrap">
        <span
          class="font-extrabold uppercase text-[32px] sm:text-5xl md:text-6xl lg:text-7xl xl:text-[98px]"
        >
          digital ally
        </span>
      </div>
    </div>

    <div
      class="absolute inset-0 top-[-1020px] sm:top-[-2300px] flex flex-col items-center justify-center gap-4 px-4 left-40 sm:hidden"
    >
      <div class="w-58 text-start mr-20 mt-90 text-[14px]">
        <span>
          We are an award-winning marketing transformation partner delivering
          <b>unforgettable</b> digital brands, experiences and technology.
        </span>
      </div>
    </div>
  </div>

  <!-- Shadow Mobile ONLY-->
  <div class="relative">
    <div
      class="absolute left-1/2 xl:block"
      :style="{
        width: '100vw',
        height: '200px',
        top: '-205px',
        transform: 'translateX(-50%)',
        background: 'linear-gradient(180deg, #01010100 0%, rgba(1,1,1,1) 100%)',
        filter: 'blur(0px)',
        zIndex: 10,
        pointerEvents: 'none',
      }"
    ></div>
  </div>

  <!-- Shadow Web -->
  <div
    class="absolute left-1/2 hidden sm:inline"
    :style="{
      width: '2000px',
      height: '1200px',
      top: '500px',
      transform: 'translateX(-50%)',
      background: 'linear-gradient(180deg, #01010100 0%, rgba(1,1,1,0.3) 100%)',
      filter: 'blur(0px)',
      zIndex: 10,
      pointerEvents: 'none',
    }"
  ></div>

  <!-- <div
    class="absolute left-1/2 xl:block"
    :style="{
      width: '100vw',
      height: '700px',
      top: '600px',
      transform: 'translateX(-50%)',
      background: 'linear-gradient(180deg, #01010100 0%, #010101 100%)',
      filter: 'blur(0px)',
      zIndex: 10,
      pointerEvents: 'none',
    }"
  ></div> -->
</template>

<style scoped>
@media (max-width: 375px) and (max-height: 740px) {
  .ip-se {
    padding-top: 15rem !important;
    bottom: 15rem !important;
  }
}

.circle-wave {
  top: 50%;
  left: 50%;
  border-width: 1px;
  pointer-events: none;
  opacity: 100%;
  transform: translate(-50%, -50%);
  animation: waveOpacity 2.5s ease-in-out infinite;
}

.circle-wave-mobile {
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.shadow-bottom-blue {
  box-shadow: 0 120px 120px 40px rgba(51, 102, 255, 0.35);
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
