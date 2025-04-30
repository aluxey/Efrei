<script setup>
import BaseButton from '../components/BaseButton.vue'
</script>

<template>
  <section class="home-page">
    <h1>Here comes the content of the HomePage.</h1>

    <BaseButton @click="alert('clicked!')">Primary action</BaseButton>
    <BaseButton disabled style="margin-left:1rem">Disabled</BaseButton>
  </section>
</template>
