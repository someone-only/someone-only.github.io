<script setup lang="ts">
import { RouterView, useRoute } from "vue-router";
import Navbar from "./components/v2/Navbar.vue";
import Footer from "./components/v2/Footer.vue";

const route = useRoute();
</script>

<template>
  <Navbar />
  <router-view v-slot="{ Component }">
    <transition name="fade">
      <component :is="Component" :key="route.fullPath" />
    </transition>
  </router-view>
  <Footer />
</template>

<style scoped></style>
