<template>
  <div>
    <h3>获奖情况</h3>
    <multirow-editor :lines="prices"></multirow-editor>
  </div>
</template>

<script>
  import multirowEditor from './multirow_editor';

  export default {
    name: "price",
    components: {multirowEditor},
    props: {
      prices: {
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
