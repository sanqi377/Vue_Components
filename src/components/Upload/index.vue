<!-- 图片上传组件 -->
<template>
  <div class="upload">
    <input
      type="file"
      accept="image/*"
      ref="upload"
      @change="getFileInfo"
    /><span class="submit" @click="submitFile()">上传图片</span>
  </div>
</template>
<script>
var fileDom;
export default {
  name: "Upload",
  methods: {
    getFileInfo: (e) => {
      fileDom = e.target;
    },
    submitFile: () => {
      let file = fileDom.files[0];
      let formdata = new FormData(); //formdata格式
      // formdata.append("picture", file); //图片文件
      formdata.append("name", "1"); //其他参数
      // formdata.append("introduce", this.product_add.introduce); //其他参数
      console.log(formdata);
      console.log(file);
      // this.$refs.validate((valid) => {
      //   //校验成功
      //   if (valid) {
      //     let myfile = this.$refs.upload;
      //     let files = myfile.files;
      //     let file = files[0];
      //     let formdata = new FormData(); //formdata格式
      //     formdata.append("picture", file); //图片文件
      //     formdata.append("name", this.product_add.name); //其他参数
      //     formdata.append("introduce", this.product_add.introduce); //其他参数
      //     console.log(formdata);
      //     //   // 发送请求
      //     //   this.axios({
      //     //     method: "POST",
      //     //     data: formdata,
      //     //     url: "/product_Description/product/addProduct",
      //     //     headers: { "Content-Type": "multipart/form-data" },
      //     //   }).then((response) => {
      //     //     this.initProduct();
      //     //     if (resp.data.code == 0) {
      //     //       this.$message({
      //     //         message: "添加产品成功！",
      //     //         type: "success",
      //     //       });
      //     //     } else {
      //     //       this.$message.error("添加产品失败！");
      //     //     }
      //     //   });
      //   }
      // });
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