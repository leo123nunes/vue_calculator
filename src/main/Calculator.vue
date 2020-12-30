<template>
    <div class="calculator">
        <Display value="1000"></Display>
        <Button label="AC" triple @onCalcButtonClick="clearMemory"></Button>
        <Button label="/" operation @onCalcButtonClick="setOperation"></Button>
        <Button label="7" @onCalcButtonClick="addDigit"></Button>
        <Button label="8" @onCalcButtonClick="addDigit"></Button>
        <Button label="9" @onCalcButtonClick="addDigit"></Button>
        <Button label="*" operation @onCalcButtonClick="setOperation"></Button>
        <Button label="4" @onCalcButtonClick="addDigit"></Button>
        <Button label="5" @onCalcButtonClick="addDigit"></Button>
        <Button label="6" @onCalcButtonClick="addDigit"></Button>
        <Button label="-" operation @onCalcButtonClick="setOperation"></Button>
        <Button label="1" @onCalcButtonClick="addDigit"></Button>
        <Button label="2" @onCalcButtonClick="addDigit"></Button>
        <Button label="3" @onCalcButtonClick="addDigit"></Button>
        <Button label="+" operation @onCalcButtonClick="setOperation"></Button>
        <Button label="0" double @onCalcButtonClick="addDigit"></Button>
        <Button label="." @onCalcButtonClick="addDigit"></Button>
        <Button label="=" operation @onCalcButtonClick="setOperation"></Button>
    </div>
  
</template>

<script>
import Button from '../components/Button.vue'
import Display from '../components/Display.vue'

export default {

    components: {Button, Display},

    methods: {
        addDigit(digit){
            console.log(`digit ${digit} has been added`)
        },

        clearMemory(){
            console.log('clean memory')
        },
        
        setOperation(operation){
            console.log(`the operation ${operation} has been set`)
        }
    }
}
</script>

<style>
:root{
    --width-calculator: 250px;
    --height-calculator: 300px;
}
.calculator{
    width: var(--width-calculator);
    height: var(--height-calculator);
    display: grid;
    border-radius: 5px;
    overflow: hidden;
    grid-template-columns: repeat(4, 25%);
    grid-template-rows: 1fr 48px 48px 48px 48px 48px;
}

</style>