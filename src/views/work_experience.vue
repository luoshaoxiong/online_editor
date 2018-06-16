<template>
  <div class="clearfix">
    <h3>工作经历</h3>
    <el-form v-for="(exp, index) in experiences" label-width="80px" label-position="left" :key="index">
      <hr v-show="index!==0"/>
      <el-form-item label="公司名称">
        <el-input v-model="exp.company"></el-input>
      </el-form-item>
      <el-form-item label="工作内容">
        <el-input type="textarea"
                  autosize
                  placeholder="请输入内容"
                  v-model="exp.works"></el-input>
      </el-form-item>
    </el-form>
    <el-button type="primary" class="add-btn" @click="addContent">添加经历</el-button>
  </div>
</template>

<script>
  export default {
    name: "experience",
    props: {
      experiences: {
        type: Array
      }
    },
    methods: {
      addContent() {
        this.experiences.push({company: '', works: ''});
      }
    }
  }
</script>

<style scoped>
  h3 {
    margin-bottom: 20px;
  }
  hr {
    border: 0.5px solid #dfdfdf;
    margin-bottom: 22px;
  }
  .add-btn {
    float: right;
  }
</style>
