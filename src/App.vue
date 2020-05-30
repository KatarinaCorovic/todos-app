<template>
  <div id="app">
    <h1>To do list</h1>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style lang="scss">
#app {

  h1{
    text-align: center;
    font-family: 'Arial', sans-serif;
    color:rgb(90, 81, 81);
  }

}
</style>
