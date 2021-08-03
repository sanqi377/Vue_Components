<template>
    <div class="number">
        <div class="btn" @click="handleCount(-1)">-</div>
        <input class="count" type="number" v-model="count" @change="handleInput"/>
        <div class="btn" @click="handleCount(1)">+</div>
    </div>
</template>

<script>
export default {
    name: "inputNumber",
    props: {
        value: {
            type: Number,
        },
        max: {
            type: Number,
        },
        min: {
            type: Number,
        },
    },
    data() {
        return {
            count: null,
        };
    },
    methods: {
        handleInput(val){
            console.log(val)
        },
        handleCount(val) {
            this.count = this.value;
            console.log(val,this.value)
            if (this.count > this.max) {
                this.$emit("handleCount", this.max);
            }
            // if (this.value >= this.max) {
            //     if (val == -1) {
            //         this.$emit("handleCount", val);
            //     }
            // } else if (this.value <= this.min) {
            //     if (val == 1) {
            //         this.$emit("handleCount", val);
            //     }
            // } else {
            //     this.$emit("handleCount", val);
            // }
        },
    },
};
</script>

<style scoped>
.number {
    width: 180px;
    height: 45px;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid #ccc;
    border-radius: 5px;
}

.number .btn {
    width: 25%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #f5f7fa;
    cursor: pointer;
}

.number .btn:first-child {
    border-right: 1px solid #ccc;
}

.number .btn:last-child {
    border-left: 1px solid #ccc;
}

.number .count {
    width: 50%;
    height: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>