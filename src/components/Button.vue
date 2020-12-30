<template>
  <button class="button" :class='{operation, double, triple}'>
    {{label}}
  </button>
</template>

<script>
export default {
  props: {
    label: String,
    operation: Boolean,
    double: Boolean,
    triple: Boolean
  }
}
</script>

<style>
button.button{
  background-color: rgb(235, 235, 235);
  padding: 0px;
  border: 1px solid #bdbdbd;
  border-left: none;
  border-top: none;
  color: rgb(0, 0, 0);
  font-size: 20px;
}

button.button:hover{
  background-color: #bdbdbd;
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
  background-color: rgb(255, 100, 28);
  color: #fff;
}

button.operation:hover{
  background-color: rgb(175, 71, 22);
}

button.button:active{
  outline: none;
  text-decoration: none;
}

</style>