<template>
  <div class="drawer-container">
    <div v-if="open" class="backdrop"></div>
    <div class="drawer" :class="{ open }">
      <nav class="mobile-nav">
        <div class="menu-header">
          <h3 class="menu-title">Menu</h3>
          <button v-if="open" class="x-button" @click="handleClose">
            <font-awesome-icon class="icon" icon="fa-xmark"></font-awesome-icon>
          </button>
        </div>
        <div>
          <ul class="list">
            <li
              v-for="item in props.navItems"
              :key="item.id"
              class="list-item"
              @click="handleClick"
            >
              {{ item.text }}
            </li>
          </ul>
        </div>
      </nav>
    </div>
  </div>
</template>
<script setup>
import { defineProps, defineEmits } from "vue";

const props = defineProps(["navItems", "open"]);
const emit = defineEmits(["close-menu"]);

const handleClose = () => emit("close-menu");
</script>
<style lang="scss" scoped>
@import "../scss/variables";
@import "../scss/mixins";

.drawer-container {
  .backdrop {
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100vw;
    background: rgba($color: #000000, $alpha: 0.75);
    z-index: 10;
  }
  .drawer {
    @include hide-visually;
    &.open {
      @include show-visually;
      position: absolute;
      height: 100vh;
      width: 60vw;
      padding: 0 24px;
      max-width: 275px;
      background: $primary;
      top: 0;
      right: -300px;
      z-index: 20;
      right: 0;
      transition: 300ms;
    }

    .mobile-nav {
      display: flex;
      flex-direction: column;
      .menu-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        .x-button {
          background: none;
          border: none;
          color: $text-primary;
          padding: 0;
          z-index: 21;
        }
      }
      .list {
        list-style-type: none;
        padding: 0;
        .list-item {
          padding: 12px 0;
        }
      }
    }
  }
  .icon {
    @include icon;
  }
}
</style>
