<template>
  <div id="app">
    <header class="header">
      
    </header>
    <body>
      <musicplayer />
      
      
    </body>
  </div>
</template>

<script>
import musicplayer from './components/musicplayer.vue'

export default {
  name: 'App',
  components: {
    musicplayer
    
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: #FFF0F5;
  text-align: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
}
.header {
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  
  background-color: #2c3e50;
  color: #ffffff;
}
body {
  min-height: 100vh;
  
}

</style>
