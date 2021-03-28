<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <FloatingPopup width="700" height="450" />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import FloatingPopup from './components/FloatingContainer.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    FloatingPopup,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway&family=Roboto&display=swap');

#app {
  /* font-family: 'Raleway', 'Roboto', Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}

</style>
