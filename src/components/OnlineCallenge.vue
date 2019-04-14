<template>
    <div class="background">
        <div class="title">Onsite Challenge</div>
        <div class="sub-title">Break out of your comfort zone.</div>
        <div v-bind:class="[sent? 'disabled': '']">
            <div class="description">Send a motivational message to another person</div>
            <div class="message">
                <v-text-field v-bind:label="'Words of affirmation...'"></v-text-field>
            </div>
            <div class="next" @click="clickNext">Send</div>
        </div>
        <div class="list" v-bind:class="[sent? '': 'disabled']">
            <div class="name">
                <span>JOHN APPLESEED</span>
            </div>
            <div class="content">
                <span>Maecenas a enim scelerisque, faucibus nisl vel, semper ex. Ut iaculis semper neque, id lobortis lacus tempus id. Praesent rutrum finibus nibh vitae volutpat. Lorem ipsum dolor sit amet.</span>
            </div>

            <div class="divider"></div>

            <div class="name">
                <span>JOSEPH SANS</span>
            </div>
            <div class="content">
                <span>Duis congue posuere rhoncus. Fusce aliquam quam ac massa euismod, vitae luctus diam lobortis. Etiam fringilla sit amet tortor et finibus. Ut sed mollis felis.</span>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Callenge",
        data: function() {
          return {
              sent: false
          }
        },
        methods: {
            clickNext: function(){
                this.sent = true;
            }
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
    .description{
        margin-top: 100px;
        color: #20405D;
        text-align: center;
    }
    .message{
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
    .list {
        margin-top: 20px;
    }
    .name {
        color: #20405D;
        font-weight: bold;
        margin-left: 15px;
    }
    .content {
        margin: 5px 16px 0;
        color: #20405D;
    }
    .divider {
        border: 2px solid #20405D;
        width: 50%;
        margin: 10px auto;
    }
</style>