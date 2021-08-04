<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png" />
        <h1>Vue 常用组件</h1>
        <Music />
    </div>
</template>

<script>
import Music from "@/components/Music"
export default {
    name: "App",
    data() {
        return {
            val: null,
        };
    },
    methods: {
        
    },
    components: {
        Music
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
