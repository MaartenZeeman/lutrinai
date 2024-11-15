<script setup lang="ts">
  import type { ChatDetails } from '@/models/chat-details';

  const props = defineProps<{
    chat: ChatDetails
  }>()

  const imgUrl = new URL(`../assets/images/avatars/${props.chat.avatar}.png`, import.meta.url).href
</script>

<template>
  {{ imgUrl }}
  <RouterLink to="/chat" class="chat">
    <img class="avatar" :src="imgUrl" alt="">
    <section class="chat-info">
        <div class="chat-header">
            <h2>{{ chat.name }}</h2>
            <time datetime="2024-10-17 13:37">{{ chat.dateActive.toLocaleString() }}</time>
        </div>
        <p class="chat-summary">{{ chat.lastQuestion }}</p>
    </section>
  </RouterLink>
</template>

<style scoped lang="scss">
  .chat {
    height: 5rem;
    padding: 6px 10px 6px 10px;
    border-bottom: 1px solid #EED2CC;
    display: flex;
    cursor: pointer;

    &.active {
        background-color: #FBF7F4;
        color: #A1683A;

        .chat-summary {
            color: #a1683aad;
        }
    }
}

.avatar {
    border-radius: 50%;
    width: 75px;
    height: 75px;
    padding: 5px;
    background-color: white;
    margin-right: 10px;
}

.chat-info {
    flex: 1 0 auto;

    .chat-header {
        display: flex;
        justify-content: space-between;

        h2 {
            color: #FBF7F4;
            font-size: 1.2rem;
        }

        time {
            font-style: italic;
        }
    }

    .chat-summary {
        color: #dbdbdb;
    }

}

a {
    color: inherit;
    text-decoration: inherit;
}
</style>
