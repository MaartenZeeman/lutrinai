<script setup lang="ts">
import { RouterView } from 'vue-router'
import SidebarComponent from './components/SidebarComponent.vue';
</script>

<template>
  <div class="container">
    <SidebarComponent class="sidebar"></SidebarComponent>
    <main class="main-content">
      <RouterView />
    </main>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  max-width: 1920px;
  max-width: 100vw;
  margin: 0 auto;
  background-color: #FBF7F4;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  min-height: 100vh;
  overflow: hidden;
}

.sidebar {
  flex: 1;
  min-width: 350px;
  background-color: #6C9A8B;
  color: #FBF7F4;
  padding: 20px 0;
}

.main-content {
  flex: 3;
  padding: 40px;
  position: relative;
  max-width: calc(100% - 430px);
}
</style>
