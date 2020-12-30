<template>
    <div class="calculator">
        <Display></Display>
        <Button label="AC" triple></Button>
        <Button label="/" operation></Button>
        <Button label="7"></Button>
        <Button label="8"></Button>
        <Button label="9"></Button>
        <Button label="*" operation></Button>
        <Button label="4"></Button>
        <Button label="5"></Button>
        <Button label="6"></Button>
        <Button label="-" operation></Button>
        <Button label="1"></Button>
        <Button label="2"></Button>
        <Button label="3"></Button>
        <Button label="+" operation></Button>
        <Button label="0" double></Button>
        <Button label="."></Button>
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
    width: 250px;
    height: 300px;
    display: grid;
    border-radius: 5px;
    overflow: hidden;
    grid-template-columns: repeat(4, 25%);
    grid-template-rows: 1fr 48px 48px 48px 48px 48px;
}

</style>