<template>
    <div class="background">
        <div class="title">Lifting Spirits</div>
        <div class="sub-title">How does this memory make you feel?</div>
        <div class="options">
            <div class="line">
                <div class="option" v-bind:class="[isEmotionSelected(emotion)? emotion: '']" @click="selectEmotion($event, emotion)"
                     :key="index" v-for="(emotion, index) in emotions.slice(0,3)">{{emotion}}</div>
            </div>
            <div class="line">
                <div class="option" v-bind:class="[isEmotionSelected(emotion)? emotion: '']" @click="selectEmotion($event, emotion)"
                     :key="index" v-for="(emotion, index) in emotions.slice(3,5)">{{emotion}}</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Feel",
        data: function() {
          return {
              emotions: ["happy", "uplifted", "excited", "content", "satisfied"],
              selected: []
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
            }
        }
    }
</script>

<style scoped>
    .background {
        background-image: url("../assets/feel.jpg");
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
        color: white;
    }
    .sub-title{
        margin: 0 auto;
        width: fit-content;
        font-size: 16px;
        color: white;
        font-weight: lighter;
        text-align: center;
    }
    .options{
        margin-top: 15px;
    }
    .line {
        margin: 0 auto;
        width: fit-content;
    }
    .option{
        color: white;
        border: 1.5px solid white;
        border-radius: 15px;
        padding: 3px 15px;
        width: fit-content;
        font-size: 13px;
        margin: 3px 4px;
        float: left;
        cursor: pointer;
    }
    .happy {
        background-color: green;
        border-color: green;
    }
    .uplifted {
        background-color: #CC1F1A;
        border-color: #CC1F1A;
    }

    .excited{
        background-color: #7886D7;
        border-color: #7886D7;
    }
    .content{
        background-color: #DE751F;
        border-color: #DE751F;
    }
    .satisfied{
        background-color: #3D4852;
        border-color: #3D4852;
    }
</style>