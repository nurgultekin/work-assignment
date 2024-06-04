<template>
  <nav class="navbar">
    <div class="navbar-left">
      <a href="https://vendre.io" class="logo">Vendre</a>
    </div>
    <div class="navbar-right">
      <button class="hamburger-btn" @click="toggleMenu">
        <i class="fas fa-bars"></i>
      </button>
      <div class="menu-links" :class="{ 'show-menu': isMenuOpen }">
        <a href="#product">Product</a>
        <a href="#partners">Partners</a>
        <a href="#pricing">Pricing</a>
        <a href="#references">References</a>
      </div>
    </div>
    <div class="navbar-right">
      <button class="language-btn"><i class="fas fa-globe"></i></button>
      <button class="cta-btn">Try it</button>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavigationBar',
  data() {
    return {
      isMenuOpen: false
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    }
  }
};
</script>

<style src="../styling/NavBar.css" scoped></style>
