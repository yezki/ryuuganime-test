<template>
  <div style="position: relative;">
    <Navbar :darkmode="darkmode" @changeDarkMode="changeMode" />
    <router-view :darkmode="darkmode" />
  </div>
</template>

<script>
  import Navbar from '@/components/Navbar.vue';

  export default {
    components: {
      Navbar
    },
    data() {
      return {
        darkmode: false
      }
    },
    methods: {
      changeMode(darkmode) {
        this.darkmode = darkmode;
        document.body.style.transition = 'background 0.3s ease';
        document.querySelector('.nav').style.transition = 'all 0.3s ease';
        if (this.darkmode === true) {
          document.body.classList.add('dark');
        } else {
          document.body.classList.remove('dark');
        }
      }
    }
  }
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
} */
</style>
