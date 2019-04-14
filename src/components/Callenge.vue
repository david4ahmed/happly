<template>
    <div class="background">
        <div class="title">Challenges</div>
        <div class="sub-title">Choose a challenge type</div>
        <div class="options">
            <div class="option" style="float:left;">onsite</div>
            <div class="option" style="float:right;">offsite</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Callenge"
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
    .options{
        width: 65%;
        margin: 50px auto;
    }
    .option{
        color: #20405D;
        border: 1.5px solid #20405D;
        border-radius: 15px;
        padding: 3px 15px;
        width: fit-content;
        font-size: 18px;
        font-weight: bold;
        margin: 3px 4px;
        cursor: pointer;
    }
</style>