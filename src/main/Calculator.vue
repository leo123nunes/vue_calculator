<template>
    <div class="calculator">
        <Display :value="displayValue"></Display>
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
    data: function(){
        return {
            values: [0,0],
            current: 0,
            displayValue: "0",
            operation: null,
            clearDisplay: true
        }
    },

    components: {Button, Display},

    methods: {
        addDigit(digit){

            if(digit == '.'){
                if(this.displayValue.toString().includes('.')){
                    return
                }
            }

            if(this.displayValue == '0'){
                if(digit == '0'){
                    return
                }
            }

            if(this.clearDisplay && digit != '.'){
                this.displayValue = ""
                this.clearDisplay = false
            }

            
            this.displayValue += digit
            this.clearDisplay = false
            this.values[this.current] = parseFloat(this.displayValue)
        },

        clearMemory(){
            this.values = [0,0],
            this.current = 0,
            this.displayValue = "0",
            this.operation = null,
            this.clearDisplay = true
        },

        setOperation(operation){
            var lastOperation = this.operation
            this.operation = operation
            this.current = 1
            this.clearDisplay = true
            var result = 0

            if(operation == '='){      
                try{
                    this.operation = lastOperation
                    result = eval(`${this.values[0]} ${this.operation} ${this.values[1]}`)
                    
                    if(result.toString().length > 11){
                        result = parseFloat(result.toString().slice(0,11))
                    }

                    this.operation = null
                   
                    if((this.values[0] == 0 || this.values[1] == 0) && lastOperation == '/'){
                        this.displayValue = 0
                        this.values[0] = null
                        this.values[1] = null
                        return
                    }else{
                        this.displayValue = result
                        this.values[0] = result
                        this.values[1] = null
                        return
                    }
                }catch(e){
                    return
                }
            }

            if(lastOperation){
                result = eval(`${this.values[0]} ${lastOperation} ${this.values[1]}`)
                
                if(result.toString().length > 11){
                        result = parseFloat(result.toString().slice(0,11))
                    }
                
                if(!isNaN(result)){
                    this.displayValue = result
                    this.values[0] = result
                    this.values[1] = null 
                    return  
                }
                if(this.values[1] == 0){
                    this.displayValue = 0
                    this.values[0] = null
                    this.values[1] = null
                }
                return
            }  
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