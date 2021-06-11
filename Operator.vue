<template>
<div>
 <button  @click="$emit('changeOperator','+')">Add (+) </button>
  <button @click="$emit('changeOperator','-')">Sub (-) </button>
  <button @click="$emit('changeOperator','*')">Multiply (*) </button>
  <button @click="$emit('changeOperator','/')">Division(/) </button>

</div>

</template>

<script>
export default {

}
</script>
<style>
</style>
