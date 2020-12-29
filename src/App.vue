<template>
    <div id="app">
        <h1>Calculator</h1>
        <Calculator></Calculator>
    </div>
</template>

<script>
import Calculator from '../src/main/Calculator.vue'

export default {
    components: {Calculator}
}
</script>

<style>
@font-face{
    font-family: "RobotoMono";
    src: url("./fonts/RobotoMono-Thin.ttf");
}

*{
    font-family: "RobotoMono";
}

body{
    display: flex;
    flex-direction: column;
    background: rgba(0, 0, 0, 0) linear-gradient(to right, rgb(0, 121, 145), rgb(120, 255, 214)) repeat scroll 0% 0%;
    justify-content: center;
    align-items: center;
    text-align: center;
    height: 100vh;
}

</style>