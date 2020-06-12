<template>
  <div id="app">
    <app-header></app-header>
    <app-main></app-main>
  </div>
</template>

<script>
import Header from './components/header/Header.vue';
import Main from './components/main/Main.vue';

export default {
  name: 'app',
  components: {
    AppHeader: Header,
    AppMain: Main
  }
}
</script>

<style lang="scss">
    #app {
      font-family: 'Nunito Sans', sans-serif;
    }
</style>
