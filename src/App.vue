<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Shykot js App"/>
 <HomePage />
</template>

<script>
import  HelloWorld from './components/HelloWorld.vue';
import HomePage from './components/HomePage.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    HomePage,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 20px;
}
</style>
