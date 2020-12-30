<template>
  <button class="button" :class='{operation, double, triple}' @click="$emit('onCalcButtonClick', label)">
    {{label}}
  </button>
</template>

<script>
export default {
  props: {
    label: {},
    operation: {type: Boolean},
    double: {type: Boolean},
    triple: {type: Boolean}
  }
}
</script>

<style>
:root{
  --background-button: #ebebeb;
  --background-button-operation: #ff641c;
  --backgroundhover-button: #bdbdbd;
  --backgroundhover-button-operation: #af4716;
}

button.button{
  background-color: var(--background-button);
  padding: 0px;
  border: 1px solid #bdbdbd;
  border-left: none;
  border-top: none;
  color: rgb(0, 0, 0);
  font-size: 1.5em;
}

button.button:hover{
  background-color: var(--backgroundhover-button);
  text-decoration: none;
  outline: none;
}

button.double{
  grid-column: span 2;
}

button.triple{
  grid-column: span 3;
}

button.operation{
  background-color: var(--background-button-operation);
  color: #fff;
}

button.operation:hover{
  background-color: var(--backgroundhover-button-operation);
}

button.button:active{
  outline: none;
  text-decoration: none;
}

</style>