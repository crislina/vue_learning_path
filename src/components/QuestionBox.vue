<template>
  <div>
    <b-jumbotron>
      <template v-slot:lead>{{ question.question }}</template>

      <hr class="my-4" />

      <b-list-group>
        <b-list-group-item 
            v-for="(answer,index) in answers" 
            :key="index"
            @click="selectAnswer(index)"
            :class="[selectedIndex === index ? 'selected':'']"
            >{{answer}}</b-list-group-item>
      </b-list-group>

      <b-button variant="primary" href="#">Submit</b-button>
      <b-button @click="next" variant="success" href="#">Next</b-button>
    </b-jumbotron>
  </div>
</template>

<script>
export default {
  props: {
    question: Object,
    next: Function
  },
  data(){
      return {
          selectedIndex:null
      }
  },
  computed: {
    answers() {
      let answers = [...this.question.incorrect_answers];
      answers.push(this.question.correct_answer);
      return answers;
    }
  },
  methods:{
      selectAnswer(index){
          this.selectedIndex=index
          console.log(index)
      }
  }
};
</script>

<style scoped>
.list-group{
    margin-bottom: 15px;
}
.list-group-item:hover{
    background: #EEE;
}
.btn{
    margin: 0 5px;
}
.selected{
    background-color: lightblue;
}
.corrected{
    background-color:lightgreen;
}
.incorrected{
    background-color:lightcoral;
}
</style>