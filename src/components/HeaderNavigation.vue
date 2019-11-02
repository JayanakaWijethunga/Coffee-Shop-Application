<template>
  <header class="border-b py-3 px-3">
    <FontAwesomeIcon icon="bars" class="text-2xl" @click="ToggleShowMenu" />
    <span id="site-logo" class="font-bold text-xl">
      Hot Coffee Shop
    </span>

    <nav v-if="ShowMenu">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
  </header>
</template>

<script>
export default {
  name: "HeaderNavigation",
  data() {
    return {
      ShowMenu: true
    };
  },
  methods: {
    ToggleShowMenu() {
      this.ShowMenu = !this.ShowMenu;
    }
  }
};
</script>
