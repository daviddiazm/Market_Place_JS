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
  position: sticky;
  padding: 20px;
  display: flex;
  gap: 2vw;
  justify-content: center;
  align-items: center;
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
