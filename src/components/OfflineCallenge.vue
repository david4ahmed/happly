<template>
    <div class="background">
        <div class="title">Offsite Challenge</div>
        <div class="sub-title">Break out of your comfort zone. </div>
        <div class="content" v-bind:class="[accept? 'disabled': '']">
            <div class="mission">Compliment 2 random people today</div>
            <div class="next" @click="acceptRequest">Accept</div>
        </div>
        <div class="content" v-bind:class="[accept? '': 'disabled']">
            <div class="mission">The Challenge</div>
            <div class="sub-title">Compliment 2 random people today</div>
            <div class="sub-title">Did you do it?</div>
            <div class="options">
                <div class="option" style="float:left;">yes</div>
                <div class="option" style="float:right;">no</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Callenge",
        data: function() {
          return {
              accept: false
          }
        },
        methods: {
            acceptRequest(){
                this.accept = true;
            },
        }
    }
</script>

<style scoped>
    .background {
        background-image: url("../assets/challenge.jpg");
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
    .options{
        width: 50%;
        margin: 50px auto;
    }
    .option{
        color: #20405D;
        border: 1.5px solid #20405D;
        border-radius: 15px;
        padding: 3px 20px;
        width: fit-content;
        font-size: 18px;
        font-weight: bold;
        margin: 3px 4px;
        cursor: pointer;
    }
    .mission {
        color: #20405D;
        font-weight: bold;
        margin-left: 15px;
        margin-bottom: 30px;
    }
    .disabled {
        display: none;
    }
    .content {
        margin-top: 50px;
    }
</style>