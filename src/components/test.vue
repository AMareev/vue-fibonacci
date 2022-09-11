<template>
    <div class="headers">
        <h1>TEST</h1>
    </div>
    <br/>
    <div class="inputs-container">
        <div>{{ inputValue }}</div>
    </div>

   <!--<canvas></canvas>-->
</template>

<script>
export default {
    name: "test",
    props: {
        inputValue: {
            type: String
        }
    }
}
</script>

<style scoped>

</style>
