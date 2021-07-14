<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png" />
        <h1>Vue 常用组件</h1>
        <Upload action="http://api.xqphp.com/admin/common/upload"/>
    </div>
</template>

<script>
import Upload from "@/components/Upload/index.vue";

export default {
    name: "App",
    components: {
        Upload,
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
