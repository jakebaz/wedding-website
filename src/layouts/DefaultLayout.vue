<template>
  <AppHeader />
  <main>
    <slot></slot>
  </main>
</template>
<script setup>
import AppHeader from "@/components/AppHeader.vue";
</script>
