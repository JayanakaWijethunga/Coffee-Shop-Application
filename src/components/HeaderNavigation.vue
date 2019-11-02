<template>
  <header class="border-b py-3 px-3">
    <FontAwesomeIcon icon="bars" class="text-2xl" @click="ToggleShowMenu" />
    <span id="site-logo" class="font-bold text-xl">
      Hot Coffee Shop
    </span>

    <transition name="menu">
      <div
        v-if="ShowMenu"
        class="menu-mask fixed z-50 top-0 left-0 w-full h-full flex bg-black-50"
        @click="closeMenu"
      >
        <div class="menu-container w-4/5 bg-white p-6 shadow-lg" @click.stop>
          <nav class="relative">
            <FontAwesomeIcon
              icon="times"
              class="text-2xl absolute top-0 right-0"
              @click="closeMenu"
            />
            <ul>
              <li>
                <router-link to="/">Home</router-link>
              </li>
              <li>
                <router-link to="/about">About</router-link>
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </transition>
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
    },
    closeMenu() {
      this.ShowMenu = false;
    }
  }
};
</script>

<style scoped>
.menu-mask {
  transition: opacity 0.2s ease;
}

.menu-container {
  transition: all 0.5s ease;
}

.menu-enter {
  opacity: 0;
}

.menu-leave-active {
  opacity: 0;
}

.menu-enter .menu-container,
.menu-leave-active .menu-container {
  -webkit-transform: translateX(-100%);
  transform: translateX(-100%);
}
</style>
