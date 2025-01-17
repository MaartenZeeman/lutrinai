<script setup lang="ts">
import SidebarChatComponent from './SidebarChatComponent.vue'

const chats = [
  {
    id: '1',
    name: 'Cody Coder',
    avatar: '1',
    dateActive: new Date('2024-10-17 13:37'),
    lastQuestion: 'What time is the meeting?',
  },
  {
    id: '2',
    name: 'Kees Kroket',
    avatar: '2',
    dateActive: new Date('2024-10-16 13:37'),
    lastQuestion: 'How do I reset my password?',
  },
  {
    id: '3',
    name: 'Sally Salaris',
    avatar: '3',
    dateActive: new Date('2024-10-16 13:37'),
    lastQuestion: 'Can I get the project update?',
  },
]
</script>

<template>
  <article class="article-container">
    <div class="logo">
      <RouterLink to="/">
        <img src="@/assets/images/logo.png" alt="Logo" />
        <h1>LutrinAI</h1>
      </RouterLink>
    </div>
    <br />
    <section class="chat-container">
      <SidebarChatComponent
        v-for="chat of chats"
        :chat="chat"
        :key="chat.id"
      ></SidebarChatComponent>
    </section>
    <section class="settings">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
        <path
          d="M495.9 166.6c3.2 8.7 .5 18.4-6.4 24.6l-43.3 39.4c1.1 8.3 1.7 16.8 1.7 25.4s-.6 17.1-1.7 25.4l43.3 39.4c6.9 6.2 9.6 15.9 6.4 24.6c-4.4 11.9-9.7 23.3-15.8 34.3l-4.7 8.1c-6.6 11-14 21.4-22.1 31.2c-5.9 7.2-15.7 9.6-24.5 6.8l-55.7-17.7c-13.4 10.3-28.2 18.9-44 25.4l-12.5 57.1c-2 9.1-9 16.3-18.2 17.8c-13.8 2.3-28 3.5-42.5 3.5s-28.7-1.2-42.5-3.5c-9.2-1.5-16.2-8.7-18.2-17.8l-12.5-57.1c-15.8-6.5-30.6-15.1-44-25.4L83.1 425.9c-8.8 2.8-18.6 .3-24.5-6.8c-8.1-9.8-15.5-20.2-22.1-31.2l-4.7-8.1c-6.1-11-11.4-22.4-15.8-34.3c-3.2-8.7-.5-18.4 6.4-24.6l43.3-39.4C64.6 273.1 64 264.6 64 256s.6-17.1 1.7-25.4L22.4 191.2c-6.9-6.2-9.6-15.9-6.4-24.6c4.4-11.9 9.7-23.3 15.8-34.3l4.7-8.1c6.6-11 14-21.4 22.1-31.2c5.9-7.2 15.7-9.6 24.5-6.8l55.7 17.7c13.4-10.3 28.2-18.9 44-25.4l12.5-57.1c2-9.1 9-16.3 18.2-17.8C227.3 1.2 241.5 0 256 0s28.7 1.2 42.5 3.5c9.2 1.5 16.2 8.7 18.2 17.8l12.5 57.1c15.8 6.5 30.6 15.1 44 25.4l55.7-17.7c8.8-2.8 18.6-.3 24.5 6.8c8.1 9.8 15.5 20.2 22.1 31.2l4.7 8.1c6.1 11 11.4 22.4 15.8 34.3zM256 336a80 80 0 1 0 0-160 80 80 0 1 0 0 160z"
        />
      </svg>
    </section>
  </article>
</template>

<style scoped lang="scss">
.article-container {
  top: 0;
  bottom: 0;
}
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
  border-top: 1px solid #eed2cc;
}

.settings {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 10px;
  display: flex;
  justify-content: flex-end;

  svg {
    width: 26px;
    height: 26px;
  }
}

a {
  color: inherit;
  text-decoration: inherit;
}
</style>
