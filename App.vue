<template>
  <div id="app">
  <h1> Mathematical Quiz App </h1>
  <OperatorQuiz @onBack="ClearOperator" v-if="!operator" :operator="operator"/>
  <Operator v-if="!operator" @changeOperator= "changeOperator" />
   </div>
</template>

<script>
import Operator from "./components/Operator.vue";
import OperatorQuiz from "./components/OperatorQuiz.vue";

export default {
  name: 'App',
  data(){
  return{
  operator: null,
  };
  },
  methods:{
  changeOperator(operator) {
  this.operator = operator;
  },
  clearOperator() {
  this.operator =null;

}
  },
  components: { Operator }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
padding: 10px;
width: 100px;
margin-right:10px;
background-color: black;
color: white;
}
</style>
