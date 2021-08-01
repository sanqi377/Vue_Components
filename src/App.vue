<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png" />
        <h1>Vue 常用组件</h1>
        <input-Number v-model="count" :min="-5" :max="5" @handleCount="handleCount" />
    </div>
</template>

<script>
import inputNumber from "@/components/inputNumber/index";
export default {
    name: "App",
    data() {
        return {
            count: 0,
        };
    },
    methods: {
        handleCount(val) {
            this.count += val;
        },
    },
    components: {
        inputNumber,
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
