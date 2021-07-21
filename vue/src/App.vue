<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld :msg="ipcTest"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
const { ipcRenderer } = window.require('electron');

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  computed: {
	ipcTest() {
      return ipcRenderer.sendSync('test-msg', 'hello');
	},
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
