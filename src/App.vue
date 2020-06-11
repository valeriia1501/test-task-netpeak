<template>
  <div id="app">
    <app-header></app-header>
  </div>
</template>

<script>
import Header from './components/header/Header.vue';

export default {
  name: 'app',
  components: {
    AppHeader: Header
  }
}
</script>

<style lang="scss">
    #app {
      font-family: 'Nunito Sans', sans-serif;
    }
</style>
