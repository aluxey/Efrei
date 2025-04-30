<script setup>
/* eslint-env vue/setup-compiler-macros */
import { ref } from 'vue'
import BaseButton from './BaseButton.vue'

const props = defineProps({
  color:  { type: String, default: 'primary' },
  action: { type: Function, required: true },
})

const pending = ref(false)

async function handleClick (evt) {
  if (pending.value) return
  const maybePromise = props.action(evt)

  if (maybePromise instanceof Promise) {
    pending.value = true
    try   { await maybePromise }
    finally { pending.value = false }
  }
}
</script>

<template>
  <BaseButton
    v-bind="$attrs"
    :color="props.color"
    :disabled="pending || $attrs.disabled"
    @click.stop.prevent="handleClick"
  >
    <span v-if="pending" class="spinner" />
    <slot />
  </BaseButton>
</template>

<style scoped>
.spinner{
  width:.9em;height:.9em;margin-right:.5em;
  border:2px solid currentColor;border-right-color:transparent;
  border-radius:50%;animation:spin .8s linear infinite;
}
@keyframes spin{to{transform:rotate(360deg)}}
</style>
