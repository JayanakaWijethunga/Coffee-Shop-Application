<template>
  <div id="app">
    <div id="nav">
      <HeaderNavigation />
    </div>
    <router-view />
    <FooterNavigation />
    <div class="bg-red-500 text-white">
      Test Tailwind
    </div>
  </div>
</template>

<style lang="postcss">
@import "assets/main.css";
</style>

<script>
import FooterNavigation from "@/components/FooterNavigation.vue";
import HeaderNavigation from "@/components/HeaderNavigation.vue";

export default {
  components: {
    FooterNavigation,
    HeaderNavigation
  }
};
</script>
