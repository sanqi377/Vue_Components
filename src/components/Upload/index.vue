<!-- 图片上传组件 -->
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
import axios from "axios";
var fileDom;
export default {
    name: "Upload",
    methods: {
        getFileInfo: (e) => {
            fileDom = e.target;
        },
        submitFile: () => {
            if (fileDom) {
                let file = fileDom.files[0];
                let formdata = new FormData(); //formdata格式
                formdata.append("file", file); //图片文件
                formdata.append("name", file.name); //其他参数
                axios({
                    method: "POST",
                    data: formdata,
                    url: "http://api.xqphp.com/admin/common/upload",
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