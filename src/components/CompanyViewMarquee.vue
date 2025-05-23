<script setup>
import { ref, watch } from 'vue'

const props = defineProps({
  imagesTop: {
    type: Array,
    required: true,
  },
  imagesCenter: {
    type: Array,
    required: true,
  },
  imagesBottom: {
    type: Array,
    required: true,
  },
  // startAnimation: {
  //   type: Boolean,
  //   default: false,
  // },
})

const sections = document.querySelectorAll('section')

;[...sections].forEach((section) => {
  const checkbox = section.querySelector('input')

  checkbox.addEventListener('change', () => {
    section.classList.toggle('enable-animation')
  })
})
</script>

<template>
  <section class="enable-animation">
    <div class="marquee">
      <ul class="marquee__content">
        <li v-for="(img, index) in imagesTop">
          <img
            :key="index"
            :src="img"
            alt="Company Logo"
            class="w-[124px] sm:w-[220px] h-[48px] sm:h-[90px] shrink-0"
          />
        </li>
      </ul>

      <ul aria-hidden="true" class="marquee__content">
        <li v-for="(img, index) in imagesTop">
          <img
            :key="index"
            :src="img"
            alt="Company Logo"
            class="w-[124px] sm:w-[220px] h-[48px] sm:h-[90px] shrink-0"
          />
        </li>
      </ul>
    </div>
  </section>

  <section class="enable-animation">
    <div class="marquee marquee--reverse">
      <ul class="marquee__content">
        <li v-for="(img, index) in imagesCenter">
          <img
            :key="index"
            :src="img"
            alt="Company Logo"
            class="w-[124px] sm:w-[220px] h-[48px] sm:h-[90px] shrink-0"
          />
        </li>
      </ul>

      <ul aria-hidden="true" class="marquee__content">
        <li v-for="(img, index) in imagesCenter">
          <img
            :key="index"
            :src="img"
            alt="Company Logo"
            class="w-[124px] sm:w-[220px] h-[48px] sm:h-[90px] shrink-0"
          />
        </li>
      </ul>
    </div>
  </section>

  <section class="enable-animation">
    <div class="marquee">
      <ul class="marquee__content">
        <li v-for="(img, index) in imagesBottom">
          <img
            :key="index"
            :src="img"
            alt="Company Logo"
            class="w-[124px] sm:w-[220px] h-[48px] sm:h-[90px] shrink-0"
          />
        </li>
      </ul>

      <ul aria-hidden="true" class="marquee__content">
        <li v-for="(img, index) in imagesBottom">
          <img
            :key="index"
            :src="img"
            alt="Company Logo"
            class="w-[124px] sm:w-[220px] h-[48px] sm:h-[90px] shrink-0"
          />
        </li>
      </ul>
    </div>
  </section>
</template>

<style scoped>
/* Marquee styles */
.marquee {
  --gap: 1rem;
  position: relative;
  display: flex;
  overflow: hidden;
  user-select: none;
  gap: var(--gap);
}

.marquee__content {
  flex-shrink: 0;
  display: flex;
  justify-content: space-around;
  gap: var(--gap);
  min-width: 100%;
}

@keyframes scroll {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(calc(-100% - var(--gap)));
  }
}

/* Pause animation when reduced-motion is set */
@media (prefers-reduced-motion: reduce) {
  .marquee__content {
    animation-play-state: paused !important;
  }
}

/* Enable animation */
.enable-animation .marquee__content {
  animation: scroll 10s linear infinite;
}

/* Reverse animation */
.marquee--reverse .marquee__content {
  animation-direction: reverse;
}

/* Pause on hover */
.marquee--hover-pause:hover .marquee__content {
  animation-play-state: paused;
}

/* Attempt to size parent based on content. Keep in mind that the parent width is equal to both content containers that stretch to fill the parent. */
.marquee--fit-content {
  max-width: fit-content;
}

/* A fit-content sizing fix: Absolute position the duplicate container. This will set the size of the parent wrapper to a single child container. Shout out to Olavi's article that had this solution 👏 @link: https://olavihaapala.fi/2021/02/23/modern-marquee.html  */
.marquee--pos-absolute .marquee__content:last-child {
  position: absolute;
  top: 0;
  left: 0;
}

/* Enable position absolute animation on the duplicate content (last-child) */
.enable-animation .marquee--pos-absolute .marquee__content:last-child {
  animation-name: scroll-abs;
}

@keyframes scroll-abs {
  from {
    transform: translateX(calc(100% + var(--gap)));
  }
  to {
    transform: translateX(0);
  }
}

/* Other page demo styles */
.marquee__content > * {
  flex: 0 0 auto;
  margin: 2px;
  border-radius: 0.25rem;
  text-align: center;
}

/* .marquee {
  border: 2px dashed lightgray;
} */

* {
  box-sizing: border-box;
}

body {
  padding: 2rem;
  width: 100%;
  min-height: 100vh;
  font-family: system-ui, sans-serif;
  font-size: 1rem;
  line-height: 1.5;
}

h1 {
  font-size: 2rem;
  font-weight: 600;
  line-height: 1.2;
  margin-block: 2rem 1rem;
}

h2 {
  font-size: 1.25rem;
  font-weight: 600;
}

section {
  margin-block: 3rem;
}

section > * + * {
  margin-block-start: 0.5rem;
}
</style>
