<template>
  <header class="header">
    <div>
      <h1 class="title">Ellie & Jake</h1>
    </div>
    <div>
      <AppNav />
    </div>
  </header>
</template>
<script setup>
import AppNav from "@/components/AppNav.vue";
</script>
<style lang="scss" scoped>
@import "../scss/variables";
@import "../scss/mixins";
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-left: 12px;
  padding-right: 12px;
  overflow: hidden;
  .title {
    @include uppercase;
    margin: 24px 0;
    letter-spacing: $title-spacing;
    font-size: $text-md;
  }
}
</style>
