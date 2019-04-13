<template>
    <div>
        <div class="title">
            How was your day?
        </div>
        <div class="question">
            <strong>Reason</strong> for My Behavior
        </div>
        <div class="answer">
            The reason why I did that is
            <div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
            </div>
        </div>

        <div class="question">
            <strong>Description</strong> of My Behavior
        </div>
        <div class="answer">
            Wha I did was
            <div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
            </div>
        </div>

        <div class="question">
            <strong>Consequence</strong> of My Behavior
        </div>
        <div class="answer">
        Because of my behavior,
            <div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
                <div class="option">happy</div>
            </div>
    </div>

    </div>
</template>

<script>
    export default {
        name: "ReflectBehavior"
    }
</script>

<style scoped>
    .title {
        text-align: left;
    }
    .question {
        text-align: left;
        width: 80%;
        margin: auto;
    }
    .answer {
        margin-bottom: 10px;
        display: inline-block;
    }
    .option {
        border-radius: 5px;
        background: cadetblue;
        padding: 3px;
        margin: 3px 5px;
        display: inline-block;
        float: left;
        color: white;
    }
</style>
