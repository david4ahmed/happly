<template>
    <div>
        <div class="title">
            How about giving compliments to <strong>user1234</strong>
        </div>

        <textarea class="message"></textarea>

        <button class="send">Send</button>

    </div>
</template>


<script>
    export default {
        name: "ComplimentUser"
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
