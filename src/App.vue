<template>
    <Fib/>
    <test :input-value="testValue"/>
    <input
        v-model="testValue"
        type="text">
</template>

<script>
import Fib from "./components/Fib";
import test from "./components/test"

export default {
    name: "App",
    components: {
        Fib, test,
    },
    data() {
        return {
            testValue: ""
        }
    }
}
</script>
