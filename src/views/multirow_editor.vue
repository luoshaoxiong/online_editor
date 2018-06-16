<template>
  <div class="clearfix">
    <el-input v-for="(item, index) in lines" class="line-input" :key="index"
              placeholder="请输入你的内容"
              v-model="item.description">
    </el-input>
    <el-button type="primary" class="add-btn" @click="addNewLine">添加一项</el-button>
  </div>
</template>

<script>
  export default {
    name: "multirow_editor",
    props: {
      lines: {
        type: Array
      }
    },
    methods: {
      addNewLine() {
        this.lines.push({description: ''});
      }
    }
  }
</script>

<style scoped>
  .line-input {
    margin-bottom: 22px;
  }
  .add-btn {
    float: right;
  }
</style>
