<template>
    <div class="calculator">
        <Display></Display>
        <Button></Button>
        <Button></Button>
        <Button></Button>
        <Button></Button>
    </div>
  
</template>

<script>
import Button from '../components/Button.vue'
import Display from '../components/Display.vue'

export default {

    components: {Button, Display}
}
</script>

<style>
.calculator{
    width: 300px;
    height: 300px;
    display: grid;
    border-radius: 5px;
    overflow: hidden;
    background-color: rgb(245, 108, 108);
    grid-template-columns: repeat(4, 25%);
    grid-template-rows: 1fr 48px 48px 48px 48px 48px;
}

</style>