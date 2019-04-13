<template>
    <div>
        <div class="title">
            How about trying something new?
        </div>
        <div class="sub-title">
            Give compliments to others!
        </div>

        <div>
            <img class="meme" src="../assets/prototype/instagram.png">
        </div>

        <textarea class="message"></textarea>

        <button class="send">Send</button>

    </div>
</template>


<script>
    export default {
        name: "ComplimentFriends"
    }
</script>

<style scoped>
    .title {
        text-align: left;
    }
    .sub-title {
        text-align: left;
        width: 80%;
        margin: auto;
    }
    .meme{
        width:100%;
    }
    .message{
        width: 100%;
        height: 50px;
    }
    .send{
        width: 80%;
    }
</style>
