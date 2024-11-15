<script setup lang="ts">
  import type { Maven } from "../models/maven"
  import { useTemplateRef } from 'vue'

  defineProps<{
    mavens: Maven[]
  }>()

  const scrollWrapper = useTemplateRef('scrollWrapper')
  function scrollRight() {
    scrollWrapper.value?.scrollBy({ left: 334, behavior: 'smooth' });
  }
</script>

<template>
  <div class="scroll-container">
    <div class="items-wrapper" ref="scrollWrapper">
      <article class="scroll-item" v-for="item of mavens" :key="item.id">
        <h2 class="name">{{item.name}}</h2>
        <div class="scroll-item-info">
          <img :src="`/src/assets/images/avatars/${item.avatar}.png`" alt="">
          <p>{{ item.description }}</p>
        </div>
        <div class="actions-container">
          <button class="btn btn-primary" v-if="item.canBeDeleted">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
              <path d="M6 6l12 12m-12 0L18 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg>
          </button>
          <button class="btn btn-primary" v-if="item.isActive">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
              <path d="M3 21v-6l13-3-13-3v-6l21 9-21 9z" />
            </svg>
          </button>
          <button class="btn btn-primary" v-if="!item.isActive">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 5v6H6v2h6v6h2v-6h6v-2h-6V5h-2z" />
            </svg>
          </button>
        </div>
      </article>
    </div>
    <button class="scroll-right" @click="scrollRight()">&#10095;</button>
  </div>
</template>

<style scoped lang="scss">
  @import "@/assets/style.scss";

  .scroll-container {
    position: relative;
    display: flex;
    align-items: center;
    overflow: hidden;
    width: 100%;
  }

  .items-wrapper {
    display: flex;
    gap: 14px;
    overflow-x: scroll;
    scroll-behavior: smooth;
    padding-right: 58px;
    padding-bottom: 10px;
    /* Space for arrow button */
  }

  .scroll-item {
    min-width: 300px;
    height: 300px;
    background-color: #ffffff;
    border-radius: 8px;
    font-size: 18px;
    box-shadow: 2px 2px 3px rgba(0, 0, 0, 0.2);
    display: flex;
    flex-direction: column;
    overflow: hidden;

    .name {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      font-size: 1.4rem;
      background-color: $color-brand-primary;
      color: $color-text-inverted
    }

    .scroll-item-info {
      padding: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      flex: 1 1 100%;

      img {
        width: 120px;
      }

      p {
        flex: 1 0 50%;
      }
    }

    .actions-container {
      flex: 1 0 auto;
      padding: 10px 10px 15px 10px;
      display: flex;
      align-items: center;
      justify-content: flex-end;
    }
  }

  .scroll-right {
    position: absolute;
    right: 10px;
    width: 48px;
    height: 48px;
    background-color: rgba(0, 0, 0, 0.6);
    color: white;
    border: none;
    border-radius: 50%;
    padding: 8px 12px;
    cursor: pointer;
    font-size: 24px;
    transition: background-color 0.3s;
  }

  .scroll-right:hover {
    background-color: rgba(0, 0, 0, 0.8);
  }
</style>
