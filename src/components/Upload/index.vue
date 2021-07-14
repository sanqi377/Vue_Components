<!-- 
    name: 图片上传组件,
    param: {
        action: 后台上传接口链接
    },
    author: @sanqi,
    data: 2021/07/14,
    github: https://github.com/sanqi377
-->
<template>
    <div class="upload">
        <input
            type="file"
            accept="image/*"
            ref="upload"
            @change="getFileInfo"
        />
        <span class="submit" @click="submitFile()">上传图片</span>
    </div>
</template>

<script>
var fileDom;
export default {
    name: "Upload",
    props: ["action"],
    methods: {
        getFileInfo: function (e) {
            fileDom = e.target;
            console.log(this.action);
        },
        submitFile: function () {
            if (fileDom) {
                let file = fileDom.files[0];
                let formdata = new FormData(); //formdata格式
                formdata.append("file", file); //图片文件
                formdata.append("name", file.name); //其他参数
                this.$http({
                    method: "POST",
                    data: formdata,
                    url: this.action,
                    headers: {
                        "Content-Type": "multipart/form-data",
                    },
                }).then((response) => {
                    console.log(response.data);
                });
            } else {
                console.log(0);
            }
        },
    },
};
</script>

<style scoped>
.upload {
    display: inline-block;
    border: 1px solid #000;
    border-radius: 5px;
    padding: 5px 8px;
}

.submit {
    display: inline-block;
    background-color: teal;
    border: 1px solid #fff;
    padding: 5px 8px;
    color: #fff;
    font-size: 12px;
    border-radius: 5px;
    cursor: pointer;
}
</style>