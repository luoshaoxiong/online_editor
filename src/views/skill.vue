<template>
  <div>
    <h3>技能描述</h3>
    <multirow-editor :lines="skills"></multirow-editor>
  </div>
</template>

<script>
  import multirowEditor from './multirow_editor';

  export default {
    name: "skill",
    components: {multirowEditor},
    props: {
      skills: {
        type: Array
      }
    }
  }
</script>

<style scoped>
  h3 {
    margin-bottom: 20px;
  }
</style>
