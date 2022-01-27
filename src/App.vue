
<template>
  <h1>My Calculator</h1>
  
  <div>
    <div class="container">
      <div class="display">
        <input type="text" id="calculator-input" v-model="input">
      </div>
    <!-- Må fikse på layout her, plasser i midten -->
      <div>
        <Buttons 
        @clear-input="clearDisplay"
        @target-value="displayValue" 
        @equation-equals="equals"
        @delete-stuff="deleteStuff"
        class="buttons"/>
      </div>
  </div>
  <Log :equations="equations"/>
  </div>

  
</template>

<script>

import Buttons from './components/Buttons.vue'
import Log from './components/Log.vue'

export default {
  name: 'App',
  components: {
    Buttons,
    Log,
  },

  methods: {
    clearDisplay() {
      this.input = '' // husk denne!!
    },
    displayValue(value) {
      this.input += value;
    },
    equals() {
      // burde ikke bruke eval
      // burde finne en annen måte
      let answer = eval(this.input)
      this.input = answer

      // this.equations = [...this.equations, answer] // spread operator
      this.equations.push(answer)
    },
    deleteStuff() {
      // vet ikke om dette her er bare spagetti
      let text = this.input;
      let result = text.slice(0, text.length-1)

      this.input = result
      
    }
  },
  data() {
    return {
      input: '',
      equations: [],
    }
  },

  computed: {
    
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

.container {
  max-width: 700px;
  margin: 20px auto;
  min-height: 500px;
  border: 1px solid black;
  overflow: auto;
  border-radius: 5px;
  background-color: lightblue;
  
}

.container > div {
  
}

.buttons {
  border: none;
  background-color: #123456;
  position: none;
  display: inline-block;
  align-content: center; 

}

#calculator-input {
        min-width: 300px;
        max-width: 400px;
        min-height: 50px;
        border: 1px black solid;
        margin-top: 20px;
        margin-bottom: 20px;
        background-color: lightgray;

        font-size: 35px;
}

</style>
