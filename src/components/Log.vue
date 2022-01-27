<template>
    <div class="log">
        <h2>Log</h2>
        <ul>
            <li v-for="(equation,index) in equations" :key="index">
                {{ equation }}
            </li>
        
        </ul>
    </div>
</template>
<script>

export default {
    name: 'Log',
    props: {
        equations: Array
    }
}

</script>


<style>
    .log {
        width: 400px;
        height: 500px;
        border: 1px solid black;
    }

</style>