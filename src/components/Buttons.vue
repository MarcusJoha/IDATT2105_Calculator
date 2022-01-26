<template>
    <section class="grid" @click="getValue">
        <button @click="clearInput()">C</button>
        <button>ANS</button>
        <button>DEL</button>
        <button>+</button>
        <button v-text="1" value=1></button>
        <button v-text="2" value=2></button>
        <button v-text="3" value="3"></button>
        <button v-text="'-'" value="-"></button>
        <button v-text="4" value="4"></button>
        <button v-text="5" value="5"></button>
        <button v-text="6" value="6"></button>
        <button v-text="'*'" value="*"></button>
        <button v-text="7" value="7"></button>
        <button v-text="8" value="8"></button>
        <button v-text="9" value="9"></button>
        <button v-text="'/'" value="/"></button>
        <button></button>
        <button v-text="0" value="0"></button>
        <button v-text="'.'" value="."></button>
        <button id="equal-sign" v-text="'='" value="="></button>
    </section>
</template>

<script>

    export default {
        name: 'Buttons',

        methods: {
            clearInput() {
                this.$emit('clear-input')
            },
            getValue(button) {
                this.$emit('target-value', button.target.value) // sender value til App.vue
            },
        },
        data() {
            
        },
        computed: {

        }

    }
    


</script>

<style scoped>
    button {
        text-align: center;
        width: 100px;
        height: 60px;
    }

    .grid {

        height: auto;
        display: grid;
        gap: 16px;
        padding: 10px;

        grid-template-areas: 
        'C ANS DEL plus'
        'one two three minus'
        'four five six mult'
        'seven eight nine dive'
        'none zero dot equal';

    }

    section {
        
    }

    button {
        font-size: 30px;
    }

    #equal-sign {
        background-color: orangered
    }

    section > button:nth-child(1) {
        grid-area: C;
    }

    section > button:nth-child(2) {
        grid-area: ANS;
    }
    section > button:nth-child(3) {
        grid-area: DEL;
    }
    section > button:nth-child(4) {
        grid-area: plus;
    }
    section > button:nth-child(5) {
        grid-area: one;
    }
    section > button:nth-child(6) {
        grid-area: two;
    }
    section > button:nth-child(7) {
        grid-area: three;
    }
    section > button:nth-child(8) {
        grid-area: minus;
    }
    section > button:nth-child(9) {
        grid-area: four;
    }
    section > button:nth-child(10) {
        grid-area: five;
    }
    section > button:nth-child(11) {
        grid-area: six;
    }
    section > button:nth-child(12) {
        grid-area: mult;
    }
    section > button:nth-child(13) {
        grid-area: seven;
    }
    section > button:nth-child(14) {
        grid-area: eight;
    }
    section > button:nth-child(15) {
        grid-area: nine;
    }
    section > button:nth-child(16) {
        grid-area: dive;
    }
    section > button:nth-child(17) {
        grid-area: none;
    }
    section > button:nth-child(18) {
        grid-area: zero;
    }
    section > button:nth-child(19) {
        grid-area: dot;
    }
    section > button:nth-child(20) {
        grid-area: equal;
    }

</style>