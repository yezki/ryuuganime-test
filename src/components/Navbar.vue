<template>
  <div :class="{ nav: true, active: isShowed, dark: darkmode }">
    <a href="">Home</a>
    <a href="">Explore</a>
    <a href="">About</a>
    <a href="">Contact</a>
    <div class="darkmode">
      <span>
        <svg xmlns="http://www.w3.org/2000/svg" class="darkmode-icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z" />
        </svg>
      </span>
      <div @click="changeDarkMode()" class="darkmode-toggle">
        <span></span>
      </div>
      <span>
        <svg xmlns="http://www.w3.org/2000/svg" class="darkmode-icon" viewBox="0 0 20 20" fill="currentColor">
          <path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z" />
        </svg>
      </span>
    </div>
  </div>
  <img class="logo-on-mobile" src="../assets/logos/ryuuganime.png" alt="Ryuuganime (Logo)" />
  <nav>
    <div id="navbar">
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
      <!-- <img src="../assets/favicon-96x96.png" alt="Ryuuganime (Logo)" /> -->
      <button @click="isShowed = !isShowed" :class="{ clicked: isShowed }">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>
  </nav>
</template>

<script>
  export default {
    props: ['darkmode'],
    emits: ['changeDarkMode'],
    data() {
      return {
        isShowed: false
      }
    },
    methods: {
      changeDarkMode() {
        this.$emit('changeDarkMode', !this.darkmode);
      }
    }
  }
</script>