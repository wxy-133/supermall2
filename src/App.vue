<template>
<div id="app">
  <router-view></router-view>
  <MainTabBar />

</div>
</template>

<script>
import MainTabBar from './components/content/mainTarbar/mainTarbar'
export default {
  name: 'App',
  components: {
    MainTabBar
  }
}
</script>

<style>
@import "./assets/css/base.css";
</style>
