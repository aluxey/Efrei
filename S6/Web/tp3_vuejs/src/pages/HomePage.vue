<script setup>
import { ref } from 'vue'
import AsyncButton from '@/components/AsyncButton.vue'

const clicks = ref(0)
function wait(ms){ return new Promise(r=>setTimeout(r,ms)) }

function variableDelay(){
  const delay = (clicks.value + 2) * 1000   // 2 s, 3 s, 4 s, …
  clicks.value++
  return wait(delay)
}
</script>

<template>
  <p>You clicked {{ clicks }} time<span v-if="clicks!==1">s</span></p>
  <AsyncButton color="warn" :action="variableDelay">
    I slow down every time ⏳
  </AsyncButton>
</template>
