<template>
  <div id="app">
    <router-view></router-view>
    <main-nav-bar></main-nav-bar>
  </div>
</template>

<script>
import MainNavBar from 'components/content/MainNavBar'

export default {
  name: 'App',
  components: {
    MainNavBar
  }
}
</script>

<style>
@import 'assets/css/base.css';
</style>
