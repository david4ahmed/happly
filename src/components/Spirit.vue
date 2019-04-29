<template>
    <div class="background">
        <div class="title">Lifting Spirits</div>
        <div class="sub-title">Choose an adjective to positively describe yourself with</div>

        <div class="response" v-bind:class="[isEmotionSelected()? 'selected': '']">
            <span class="result">{{getResultMessage()}}</span>
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
    </div>
</template>

<script>
    export default {
        name: "Spirit",
        data: function() {
          return {
              emotions: ["ambitious", "courteous", "generous", "reliable", "sincere"],
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
                if (emotion == null || emotion == undefined){
                    return this.selected.length > 0;
                }

                return this.selected.includes(emotion);
            },
            getResultMessage(){
                var list = "";
                if (this.selected.length == 0){
                    return "";
                }else if (this.selected.length == 1){
                    list = this.selected[0];
                }else if (this.selected.length == 2){
                    list = this.selected.join(" and ");
                }else {
                    list = this.selected.slice(0, this.selected.length-1).join(", ") + ", and " + this.selected[this.selected.length-1];
                }

                return "You are " + list + ".";
            }
        }
    }
</script>

<style scoped>
    .background {
        background-image: url("../assets/spirit.jpg");
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
        width: 77%;
        font-size: 16px;
        font-weight: lighter;
        text-align: center;
        color: white;
    }
    .response {
        width: 90%;
        height: 141px;
        margin: 50px auto 0;
        padding: 90px 5px 190px 5px;
        border-radius: 10px;
    }
    .response.selected{
        background-color: #ffffff4d;
    }
    .response .result {
        color: white;
        font-size: 15px;
        text-align: center;
        width: 100%;
        height: 37px;
        display: block;
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
        padding: 3px 11px;
        width: fit-content;
        font-size: 13px;
        margin: 6px 3px;
        float: left;
        cursor: pointer;
    }
    .selected {
        background-color: green;
        border-color: green;
    }
    .ambitious {
        background-color: #CC1F1A;
        border-color: #CC1F1A;
    }

    .courteous{
        background-color: #7886D7;
        border-color: #7886D7;
    }
    .generous{
        background-color: #DE751F;
        border-color: #DE751F;
    }
    .reliable{
        background-color: #3D4852;
        border-color: #3D4852;
    }
    .sincere{
        background-color: #38A89D;
        border-color: #38A89D;
    }

</style>