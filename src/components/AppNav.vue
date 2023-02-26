<template>
  <div class="navigation">
    <div v-if="!drawerOpen" class="burger-icon">
      <button class="burger-button" @click="handleToggleDrawer">
        <font-awesome-icon class="icon" icon="fa-bars"></font-awesome-icon>
      </button>
    </div>
    <div class="mobile-navigation">
      <MobileMenu
        :navItems="navItems"
        :open="drawerOpen"
        @close-menu="handleToggleDrawer"
      />
    </div>
    <nav class="desktop-nav">
      <ul class="list">
        <li
          v-for="item in navItems"
          :key="item.id"
          class="list-item"
          @click="handleClick"
        >
          {{ item.text }}
        </li>
      </ul>
    </nav>
  </div>
</template>
<script setup>
import { ref } from "vue";
import MobileMenu from "@/components/MobileMenu.vue";
const navItems = [
  {
    text: "Welcome",
    sectionId: "welcome",
    id: 0,
  },
  {
    text: "Catering",
    sectionId: "catering",
    id: 1,
  },
  {
    text: "Location",
    sectionId: "location",
    id: 2,
  },
  {
    text: "Contact",
    sectionId: "contact",
    id: 3,
  },
  {
    text: "Schedule",
    sectionId: "schedule",
    id: 4,
  },
];

const drawerOpen = ref(false);

const handleToggleDrawer = () => (drawerOpen.value = !drawerOpen.value);

const handleClick = (sectionId) => console.log(sectionId);
</script>
<style lang="scss">
@import "../scss/mixins";
@import "../scss/variables";
.burger-icon {
  @include min-width(md) {
    @include hide-visually();
  }
  .burger-button {
    background: none;
    border: none;
    color: $text-primary;
  }
  .icon {
    @include icon;
  }
}
.desktop-nav {
  @include hide-visually();
  @include min-width(md) {
    @include show-visually();
    .list {
      display: flex;
      &-item {
        list-style-type: none;
        margin-left: 16px;
      }
    }
  }
}
</style>
