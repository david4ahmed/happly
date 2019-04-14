<template>
    <div class="background">
        <div class="title">Talk with Happly</div>
        <div class="sub-title">Choose an adjective to positively describe yourself with</div>

        <div class="sms">
            <a class="sms" href="tel:+13127414309">
                <img src="../assets/sms.png" height="50" width="50">
            </a>
        </div>

        <div class="sms">
            <a class="sms" href="tel:+13237414309">
                <img src="../assets/phone.png" height="45" width="45">
            </a>
        </div>

        <div class="sms">
            <a class="sms" href="https://assistant.google.com/services/a/uid/0000005c62824303?hl=enhttps://assistant.google.com/services/a/uid/0000005c62824303?hl=en&source=web&source=web" target="_blank">
                <img src="../assets/google_mini.png" height="45" width="45">
            </a>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Contract",
        data: function() {
          return {
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
    .response .result {
        color: white;
        font-size: 15px;
        text-align: center;
        width: 100%;
        height: 37px;
        display: block;
    }
    .sms {
        height: 50px;
        width: 50px;
        margin: 40px auto 0;
        user-select: none;
    }

</style>