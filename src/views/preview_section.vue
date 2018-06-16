<template>
  <div>
    <span class="tag"><slot name="tag"></slot></span>
    <div class="content">
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script>
  export default {
      name: "preview_section"
  }
</script>

<style scoped>
  .tag {
    position: relative;
    display: inline-block;
    padding: 2px 10px 2px 15px;
    margin-left: 20px;
    background-color: #0086b3;
    color: #fff;
    font-size: 13px;
  }
  .tag::before {
    content: '';
    position: absolute;
    top: 23px;
    left: 0;
    border-top: 4px solid #0086b3;
    border-right: 7px solid #0086b3;
    border-bottom: 4px solid transparent;
    border-left: 7px solid transparent;
  }
  .tag::after {
    content: '';
    position: absolute;
    top: 0px;
    right: -23px;
    border-top: 11.5px solid transparent;
    border-right: 11.5px solid transparent;
    border-bottom: 11.5px solid #0086b3;
    border-left: 11.5px solid #0086b3;
  }
  .content {
    margin-left: 34px;
    margin-right: 30px;
    font-size: 13px;
    color: #333;
    border-left: 1px solid #aaa;
    border-top: 1px solid #aaa;
    padding: 10px 0;
  }
</style>
