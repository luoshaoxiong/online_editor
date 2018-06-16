<template>
  <div class="top-bar clearfix" v-show="show.topBar">
    <h1><span>V</span>ue<span>E</span>ditor</h1>
    <el-button type="primary" class="preview-btn" @click="preview">预览</el-button>
  </div>
</template>

<script>
  export default {
    name: "top_bar",
    props: ['show'],
    methods: {
      preview() {
        this.show.topBar = false;
        this.show.editor = false;
        this.show.preview = true;
      }
    }
  }
</script>

<style scoped>
  .top-bar {
    height: 80px;
    background-color: #333;
    border-bottom: 5px solid #55a532;
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
  h1>span {
    color: #55a532;
  }
</style>
