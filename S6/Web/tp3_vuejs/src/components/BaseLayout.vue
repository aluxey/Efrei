<script setup>
import BaseHeader from './BaseHeader.vue'
import BaseFooter from './BaseFooter.vue'
</script>

<template>
  <div class="app-shell">
    <BaseHeader />
    <!-- Default slot for page content -->
    <slot />
    <BaseFooter />
  </div>
</template>

<style scoped>
.app-shell {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>
