<template>
    
    <input @clear-input="clearDisplay" type="text" id="calculator-input" v-model="input">   

    <button v-bind:onClick="clearDisplay">clear</button> 
</template>

<script>

    export default {
        name: 'Display',
        components: {

        },
        data() {
            return {
                input: ''
            }
        },

        methods: {
            clearDisplay() {
                this.input = '';
            }
        }
    }
</script>

<style>

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