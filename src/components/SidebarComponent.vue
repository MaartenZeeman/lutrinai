<script setup lang="ts">
  import SidebarChatComponent from './SidebarChatComponent.vue';
    
  const chats = [
    {
      id: "1",
      name: "Cody Coder",
      avatar: "1",
      dateActive: new Date("2024-10-17 13:37"),
      lastQuestion: "What time is the meeting?",
    },
    {
      id: "2",
      name: "Kees Kroket",
      avatar: "2",
      dateActive: new Date("2024-10-16 13:37"),
      lastQuestion: "How do I reset my password?",
    },
    {
      id: "3",
      name: "Sally Salaris",
      avatar: "3",
      dateActive: new Date("2024-10-16 13:37"),
      lastQuestion: "Can I get the project update?",
    }]
</script>

<template>
  <article>
    <div class="logo">
        <RouterLink to="/">
            <img src="@/assets/images/logo.png" alt="Logo">
            <h1>LutrinAI</h1>
        </RouterLink> 
    </div>
    <br />
    <section class="chat-container">
        <SidebarChatComponent v-for="chat of chats" :chat="chat" :key="chat.id"></SidebarChatComponent>
    </section>
  </article>
</template>

<style scoped lang="scss">
  .logo {
      text-align: center;
      margin-bottom: 20px;

      h1 {
          color: #fff;
          font-size: 2rem;
      }

      img {
          border-radius: 50%;
          width: 120px;
          height: 120px;
          padding: 10px;
          object-fit: cover;
          background-color: white;
      }
  }

  .chat-container {
      display: flex;
      flex-direction: column;
      border-top: 1px solid #EED2CC;
  }

  a {
      color: inherit;
      text-decoration: inherit;
  }
</style>
