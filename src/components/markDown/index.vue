<template>
    <v-md-editor v-model="text" @change="change" height="400px"></v-md-editor>
</template>

<script>
import "./main";
export default {
    name: "markDown",
    props: {
        val: {
            type: String,
        },
    },
    data() {
        return {
            text: "",
        };
    },
    methods: {
        change(text, html) {
            this.$emit("change", { text, html });
        },
    },
};
</script>