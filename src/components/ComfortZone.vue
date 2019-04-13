<template>
    <div>
        <div class="title">
            How about trying something new?
        </div>
        <div class="sub-title">
            Switch up your routine!
        </div>

        <table class="food">
            <tr>
                <td><img class="preview" src="../assets/prototype/f1.jpg"></td>
                <td>Milk & Honey Cafe</td>
            </tr>
            <tr>
                <td><img class="preview" src="../assets/prototype/f2.jpg"></td>
                <td>sweetgreen</td>
            </tr>
            <tr>
                <td><img class="preview" src="../assets/prototype/f3.jpg"></td>
                <td>Founding Farmers - Washington</td>
            </tr>
        </table>

        <div class="resource">from yelp.com</div>
    </div>
</template>

<script>
    export default {
        name: "ComfortZone"
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
    .food {
        text-align: left;
    }
    .resource{
        text-align: right;
        color: grey;
        font-size: 10px;
    }
    .preview{
        width: 20px;
    }
</style>
