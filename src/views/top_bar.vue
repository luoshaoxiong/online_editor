<template>
    <div class="top-bar clearfix">
      <h1>在线编辑器</h1>
      <el-button type="primary" class="preview-btn">预览</el-button>
    </div>
</template>

<script>
    export default {
        name: "top_bar"
    }
</script>

<style scoped>
  .top-bar {
    height: 80px;
    background-color: #333;
  }
  .preview-btn {
    float: right;
    margin: 21px 30px 21px 0;
  }
  h1 {
    float: left;
    margin: 10px 0 0 30px;
    color: #fff;
  }

</style>
