<script setup>
import { ref, watch } from 'vue'

const props = defineProps({
  images: {
    type: Array,
    required: true,
  },
  startAnimation: {
    type: Boolean,
    default: false,
  },
})

const visible = ref(false)

watch(
  () => props.startAnimation,
  (val) => {
    if (val) visible.value = true
  },
)
</script>

<template>
  <div ref="container" class="overflow-hidden mt-10 w-full">
    <div
      ref="row"
      class="flex items-center gap-4 transition-transform -ml-[1089px] sm:-ml-[670px]"
      :class="{ 'animate-scroll-row': visible }"
    >
      <img
        v-for="(img, index) in images"
        :key="index"
        :src="img"
        alt="Company Logo"
        class="w-[124px] sm:w-[220px] h-[48px] sm:h-[90px] shrink-0"
      />
    </div>
  </div>
</template>

<style scoped>
@keyframes scrollRow {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(calc(115px * 6)); /* move left */
  }
}

@media (max-width: 640px) {
  @keyframes scrollRow {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(calc(183px * 6)); /* move left for mobile */
    }
  }
}

.animate-scroll-row {
  animation: scrollRow 5s linear forwards;
}
</style>
