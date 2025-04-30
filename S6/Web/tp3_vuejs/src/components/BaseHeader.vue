<script setup>
</script>

<template>
  <header class="header">
    <nav>
      <a href="/" class="brand">
        <i class="fa fa-home"></i> Home
      </a>

      <span class="spacer" />
      <span class="user">👋 John Doe</span>

      <button class="login-btn">Not logged in</button>
    </nav>
  </header>
</template>

<style scoped>
.header {
  background: #009688;
  color: #fff;
  padding: 0.75rem 1rem;
}
nav { display: flex; align-items: center; gap: 1rem; }
.brand { font-weight: 600; color: inherit; text-decoration: none; }
.spacer { flex: 1 1 auto; }
.login-btn { background: #00695c; border: none; color: inherit; padding: .5rem 1rem; }
</style>
