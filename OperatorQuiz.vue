<template>
<div>
<div v-if="isQuizStarted">
 <h4> {{operandLeft}} {{operator}} {{operandRight}}</h4>
 <button @click="selectAnswer(answers)" v-for="answer of answers" :key="answer">{{answer}}</button>
</div>

<div v-if="!isQuizStarted">
<button @click="StartQuiz">Start</button>
</div>
<button @click="$emit('onBack')">Back</button>

</div>
</template>
<script>
export default{
props: ["operator"],
data(){
return{
operandLeft:null,
operandRight:null,
answers:[],
expectedAnswer: null,
};
},
methods:{
    selectAnswer(answerSelected) {
        if (answerSelected === this.expectedAnswer){
            this.StartQuiz();
            }
            else {
                alert('WRONG ANSWER');
                }

},
    StartQuiz(){
this.isQuizStarted = true;
this.operandLeft = parseInt(Math.random() *13);
this.operandRight = parseInt(Math.random() *13);
const methods = {
    '+': (a,b) => a+b,
    '-': (a,b) => a-b,
    '*': (a,b) => a*b,
    '/': (a,b) => a/b,
}
const methodToUse = methods[this.operator];

for(let i =0;i<5;i++){
const answers = methodToUse;
  (parseInt(Math.random() *3),
  parseInt(Math.random() *3));
this.answers.push(answer);
}
const expectedAnswer = methodToUse(this.operandLeft,this.operandRight)
this.answers[
    parseInt(Math.random() * this.answers.length)
    ]=expectedAnswer;
    this.expectedAnswer = expectedAnswer;
}
}
};
</script>