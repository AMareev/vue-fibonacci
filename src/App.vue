<template>
    <div class="headers">
        <h1>Ряд Фибоначчи</h1>
    </div>
    <br/>
    <div class="inputs-container">
        <input
            :class="{'wrong-input': !isValid}"
            v-model="myValue"
            @input="validate"
            @keyup.enter="wtfFib"
            type="text"

        />
    </div>
    <div class="buttons-container">
        <button class="btn-1" @click="wtfFib">button-1</button>
<!--        <button class="btn-2">button-2</button>-->
        <!-- <button class="btn-1">button-3</button>
        <button class="btn-2">button-4</button>
        <button class="btn-1">button-5</button> -->
    </div>
    <div class="output">
        <div>{{ fibStart }}</div>
    </div>

</template>

<script>
export default {
    data() {
        return {
            fibStart: null,
            myValue: "",
            isValid: true
        };
    },
    methods: {
        wtfFib() {
            if (!this.isValid) {
               // this.isValid = false
                this.fibStart = "Wrong Value";
               // this.fibStart = ""
                return;
            }
            this.fibStart = 0;
            let next = 1;
            for (let fibNumber = 0; fibNumber < +this.myValue; fibNumber++) {
                let temp = next;
                next = this.fibStart + next;
                this.fibStart = temp;
            }
        },
        validate() {
            this.isValid = !isNaN(+this.myValue);
            console.log(this.isValid)
        }
    }
}


</script>

<style>
.buttons-container {
    padding: 0 14px;
}
.inputs-container,
.output {
    padding: 10px 14px;
}

.inputs-container input {
    width: 100%;
}

.inputs-container,
.buttons-container,
.headers,
.output {
    display: flex;
    justify-content: center;
}
.output {
    font-size: 44px;
    letter-spacing: 2px;
    color: crimson;
    text-shadow: 0 1px 4px rgba(0, 0, 0, 0.2);
}

.wrong-input {
    background: #ffc137;
    border-color: #42b983;
    color: #000000;
    caret-color: #42b983;
}
</style>
