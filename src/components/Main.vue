<template>
    <div class="background">
        <img class="loading" src="../assets/loading.gif" height="50" width="50">
    </div>
</template>

<script>
    export default {
        name: "Main"
    }
</script>

<style scoped>
    .background {
        background-image: url("../assets/main.png");
        background-repeat: no-repeat;
        background-size: contain;
        width: 100%;
        height: 100%;
    }
    .loading {
        position: absolute;
        left: 125px;
        top: 112px;
        user-select: none;
    }
</style>