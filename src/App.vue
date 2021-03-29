<template>
  <Paragraph msg="Simple, traffic-based pricing" size="40" fontcolor="2a536b" fontweight="500"/>
  <Paragraph msg="Sign-up for our 30-day trial. No credit card required." size="20" fontcolor="7a7a7a"/>
  <FloatingPopup width="700" height="450" />
</template>

<script>
import Paragraph from './components/ParaG.vue'
import FloatingPopup from './components/FloatingContainer.vue'

export default {
  name: 'App',
  components: {
    Paragraph,
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
