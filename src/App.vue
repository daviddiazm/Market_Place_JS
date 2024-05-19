<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <img src="@/assets/imgs/camarin_blanco3.png" alt="logo" class="logo">
    

    <div class="wrapper">

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/StudentDetail">StudentDetail</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  width: 100vw;
  position: fixed;
  z-index: 5;
  padding: 20px;
  display: flex;
  gap: 2vw;
  justify-content: space-around;
  align-items: center;
  backdrop-filter: blur(5px);
}

nav {

  display: flex;
  align-items: center;
  justify-content: center;
  gap: 2vw;
}

.logo {
  width: 50px;
}
</style>
