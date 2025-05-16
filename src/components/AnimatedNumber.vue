<template>
  <span ref="el" :class="customClass"
    >{{ displayValue }}<span v-if="suffix">{{ suffix }}</span></span
  >
</template>

<script setup>
import { ref, onMounted } from 'vue'

const props = defineProps({
  value: { type: Number, required: true },
  duration: { type: Number, default: 1500 },
  decimals: { type: Number, default: 0 },
  suffix: { type: String, default: '' },
  customClass: { type: String, default: '' },
})

const displayValue = ref(0)
const el = ref(null)
const hasAnimated = ref(false)

function animateNumber() {
  const start = 0
  const end = props.value
  const duration = props.duration
  const frameRate = 1000 / 60
  const totalFrames = Math.round(duration / frameRate)
  let frame = 0

  const counter = setInterval(() => {
    frame++
    let current = start + ((end - start) * frame) / totalFrames
    displayValue.value = props.decimals > 0 ? current.toFixed(props.decimals) : Math.round(current)
    if (frame >= totalFrames) {
      displayValue.value = props.decimals > 0 ? end.toFixed(props.decimals) : end
      clearInterval(counter)
    }
  }, frameRate)
}

onMounted(() => {
  const observer = new window.IntersectionObserver(
    (entries) => {
      if (entries[0].isIntersecting && !hasAnimated.value) {
        hasAnimated.value = true
        animateNumber()
        observer.disconnect()
      }
    },
    { threshold: 0.3 },
  )
  if (el.value) {
    observer.observe(el.value)
  }
})
</script>
