<template>
  <div id="app">
    <wrapper></wrapper>
    <div class="wrapper"></div>
  </div>
</template>

<script>
  import Main from './components/Main.vue'
export default {
  name: 'app',
  data() {
    return {}
  },
  components: {
    wrapper: Main
  }

}
</script>

<style>

  html {
    background-color: #4b5151;

  }
#app {
  align-items: center;
  background-color: #4b5151;
  color: #5a5a5a;
  display: flex;
  font-family: Helvetica, Arial, sans-serif;
  font-size: 17px;
  justify-content: center;
  height: 100%;
  margin: -10px;
}

</style>
