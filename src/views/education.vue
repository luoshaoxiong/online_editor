<template>
  <div>
    <h3>教育经历</h3>
    <multirow-editor :lines="educations"></multirow-editor>
  </div>
</template>

<script>
  import multirowEditor from './multirow_editor';

  export default {
    name: "education",
    components: {multirowEditor},
    props: {
      educations: {
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
