<template>
  <div>
    <h3>基本信息</h3>
    <el-form ref="form" :model="form" label-width="80px" label-position="left">
      <el-form-item label="姓名">
        <el-input v-model="form.name" clearable></el-input>
      </el-form-item>
      <el-form-item label="性别">
        <el-input v-model="form.sex" clearable></el-input>
      </el-form-item>
      <el-form-item label="学历">
        <el-input v-model="form.education" clearable></el-input>
      </el-form-item>
      <el-form-item label="城市">
        <el-input v-model="form.city" clearable></el-input>
      </el-form-item>
      <el-form-item label="求职意向">
        <el-input v-model="form.prefer" clearable></el-input>
      </el-form-item>
      <el-form-item label="工作年限">
        <el-input v-model="form.workingYears" clearable></el-input>
      </el-form-item>
      <el-form-item label="联系电话">
        <el-input v-model="form.phone" clearable></el-input>
      </el-form-item>
      <el-form-item label="邮箱">
        <el-input v-model="form.email" clearable></el-input>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
  export default {
    name: "user_message",
    props: {
      form: {
        type: Object
      }
    }
  }
</script>

<style scoped>
  h3 {
    margin-bottom: 20px;
  }
</style>
