
<template>
  <h1>My Calculator</h1>
  
  <div>
    <div class="container">
      <div class="display">
        <Display></Display>
      </div>
    <!-- Må fikse på layout her, plasser i midten -->
      <div class="buttons">
        <Buttons></Buttons>
      </div>
  </div>

  <Log></Log>
  </div>

  
</template>

<script>
import Display from './components/Display.vue'
import Buttons from './components/Buttons.vue'
import Log from './components/Log.vue'

export default {
  name: 'App',
  components: {
    Display,
    Buttons,
    Log,
  }
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

.container {
  max-width: 700px;
  margin: 20px auto;
  min-height: 500px;
  border: 1px solid black;
  overflow: auto;
  border-radius: 5px;
  
}



.buttons {
  border: none;
  background-color: #123456;
}
</style>
