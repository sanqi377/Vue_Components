<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png" />
        <h1>Vue 常用组件</h1>
        <markDown v-model="val" @change="change" />
    </div>
</template>

<script>
import markDown from "@/components/markDown";
export default {
    name: "App",
    data() {
        return {
            val: null,
        };
    },
    methods: {
        change(val) {
            console.log(val.text, val.html);
        },
    },
    components: {
        markDown,
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    /* text-align: center; */
    color: #2c3e50;
    margin-top: 60px;
}
</style>
