<template>
    <div class="background">
        <div class="title">Mindful Behavior</div>
        <div class="sub-title">{{selectedDescription}}</div>
        <div class="response">
            <div class="element" v-bind:class="[!isSelected(index)? 'disabled': '']" :key="index" v-for="(question, index) in questions">
                <v-text-field v-bind:label="question.placeholder" v-model="question.answer"></v-text-field>
            </div>

            <div class="next" @click="clickNext" v-bind:class="[isQuestionEnd()? 'disabled': '']">Next</div>
        </div>


        <div class="review" v-bind:class="[!isSelected(3)? 'disabled': '']">
            <div class="review_title">Review</div>
            <div class="question">
                <span>What did you do?</span>
            </div>
            <div class="response">
                <span>{{questions[0].answer}}</span>
            </div>

            <div class="divider"></div>

            <div class="question">
                <span>Why did you do it?</span>
            </div>
            <div class="response">
                <span>{{questions[1].answer}}</span>
            </div>

            <div class="divider"></div>

            <div class="question">
                <span>How can you improve?</span>
            </div>
            <div class="response">
                <span>{{questions[2].answer}}</span>
            </div>

            <div class="divider"></div>

            <div class="reflection">
                <span>Reﬂection</span>
            </div>
            <div class="response">
                <span>You completed your reflection for this task. We’ll remind about it again in a few days.</span>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        name: "Mindful",
        data: function() {
          return {
              default_question : "What have you done, and how can you improve?",
              questions: [
                  {
                      description: "Type in what you did below.",
                      placeholder: "What have you done?",
                      answer: ""
                  },
                  {
                      description: "Describe your reaction. ",
                      placeholder: "How did it go?",
                      answer: ""
                  },
                  {
                      description: "What can be done differently?",
                      placeholder: "How can you improve?",
                      answer: ""
                  }
              ],
              index: -1,
          }
        },
        computed: {
            selectedDescription: function() {
                if (this.index < 0){
                    return this.default_question;
                }
                if (this.isQuestionEnd()){
                    return "";
                }

                return this.questions[this.index].description;
            }
        },
        methods: {
            selectEmotion(e, emotion){
                if (this.isEmotionSelected(emotion)) {
                    var index = this.selected.indexOf(emotion);
                    this.selected.splice(index, 1);

                }else{
                    this.selected.push(emotion)
                }
            },
            isEmotionSelected(emotion){
                return this.selected.includes(emotion);
            },
            clickNext(){
                this.index++;
            },
            isSelected(index){
                return this.index == index;
            },
            isQuestionEnd(){
                return this.index >= 3;
            }
        }
    }
</script>

<style scoped>
    .background {
        background-image: url("../assets/mindful.jpg");
        background-repeat: no-repeat;
        background-size: cover;
        height: 100%;
        user-select: none;
    }
    .title {
        padding-top: 63px;
        margin: 0 auto;
        width: fit-content;
        font-size: 21px;
        font-weight: bold;
        color: #20405D;
    }
    .sub-title{
        margin: 0 auto;
        width: fit-content;
        font-size: 16px;
        color: #20405D;
        text-align: center;
    }
    .element {
        width: 90%;
        margin: auto;
    }
    .next{
        color: #20405D;
        border: 1.5px solid #20405D;
        border-radius: 15px;
        padding: 3px 15px;
        width: 100px;
        font-size: 15px;
        cursor: pointer;
        text-align: center;
        margin: auto;
    }
    .disabled {
        display: none;
    }
    .review {
        background-color: #ffffff4d;
        padding: 10px 5px 25px 5px;
        border-radius: 10px;
        margin: 15px 5px 5px;
    }
    .review_title{
        margin: 0 auto;
        width: fit-content;
        font-size: 21px;
        font-weight: bold;
        color: #20405D;
        margin-bottom: 10px;
    }
    .question {
        color: #20405D;
        font-weight: bold;
        margin-left: 15px;
    }
    .response {
        margin: 5px 16px 0;
        color: #20405D;
    }
    .divider {
        border: 2px solid #20405D;
        width: 50%;
        margin: 10px auto;
    }
    .reflection{
        color: #20405D;
        font-weight: bold;
        margin-left: 15px;
    }
</style>