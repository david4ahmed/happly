<template>
    <div>
        <div class="title">
            How about starting conversation with
        </div>
        <div class="name">David Ahmed</div>
        <div style="text-align: left;">with</div>
        <div>How is your day been?</div>

        <textarea class="message"></textarea>

        <button class="send">Send</button>

        <div>
            <img class="meme" src="../assets/prototype/friend.png">
        </div>
    </div>
</template>

<script>
    export default {
        name: "Memory"
    }
</script>

<style scoped>
    .title {
        text-align: left;
    }
    .message{
        width: 100%;
        height: 50px;
    }
    .send{
        width: 80%;
    }
    .meme{
        width:100%
    }
</style>