<template>
  <el-input v-bind="$attrs" v-on="$listeners" class="input-simple"></el-input>
</template>

<script>
  export default {
    name: "InputSimple",
    inheritAttrs: false
  }
</script>

<style lang="scss">
  .input-simple {
    .el-input__inner {
      background: transparent;
      line-height: 20px;
      height: 20px;
      font-size: 14px;
      color: var(--color-text);
      border: none;
      padding: 0;
    }
  }
</style>
