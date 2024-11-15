<script setup lang="ts">
  import MavenScrollComponent from '../components/MavenScrollComponent.vue'

  const activeMavens = Array.from({ length: 5 }, (_, i) => {
    return {
      id: `${i}`,
      name: "Chatty McChat",
      avatar: `${i + 1}`,
      description: "I am the smartest person in the world. I know a lot of smart people, some smarter than others, but I'm smarter than all of them. ",
      isActive: true,
      canBeDeleted: true
    }
  });

  const popularMavens = Array.from({ length: 15 }, (_, i) => {
    return {
      id: `${i}`,
      name: "Chatty McChat",
      avatar: `${i + 6}`,
      description: "I am the smartest person in the world. I know a lot of smart people, some smarter than others, but I'm smarter than all of them.",
      isActive: false,
      canBeDeleted: false
    }
  });
</script>

<template>
  <main>
    <section class="maven-selection">
      <h1>Your Mavens </h1>
      <MavenScrollComponent :mavens="activeMavens"></MavenScrollComponent>
    </section>

    <section class="maven-selection">
      <h1>Popular Mavens </h1>
      <MavenScrollComponent :mavens="popularMavens"></MavenScrollComponent>
    </section>
  </main>
</template>

<style scoped>
  h1 {
    font-size: 2rem;
  }

  .maven-selection {
    margin-bottom: 50px;
  }
</style>
