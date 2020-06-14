<template>
  <div id="app">
    <app-header></app-header>
    <app-main></app-main>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Header from './components/header/Header.vue';
import Main from './components/main/Main.vue';
import Footer from './components/footer/Footer.vue';

export default {
  name: 'app',
  components: {
    AppHeader: Header,
    AppMain: Main,
    AppFooter: Footer
  }
}
</script>

<style lang="scss">
    #app {
      font-family: 'Nunito Sans', sans-serif;
    }
</style>
