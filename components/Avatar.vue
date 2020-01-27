<template>
  <el-avatar v-bind="$attrs" v-on="$listeners" class="avatar" :class="{ online: online }"></el-avatar>
</template>

<script>
  export default {
    name: "Avatar",
    inheritAttrs: false,
    props: {
      online: {
        type: Boolean,
        require: false,
        default: false
      }
    }
  }
</script>

<style lang="scss">
  .avatar {
    width: 55px;
    height: 55px;
    overflow: initial;
    border: 2px solid var(--color-border);

    &.online {
      position: relative;

      &::before {
        content: '';
        width: 14px;
        height: 14px;
        background: var(--color-primary-lighting);
        position: absolute;
        top: 0;
        right: 2px;
        border-radius: 50%;
      }

      &::after {
        content: '';
        width: 3px;
        height: 3px;
        background: var(--color-primary-lighting);
        position: absolute;
        top: 11px;
        right: 0;
        border-radius: 50%;
      }
    }

    &.el-avatar--large {
      width: 98px;
      height: 98px;
      border-width: 4px;

      &.online {
        &::before {
          width: 22px;
          height: 22px;
          top: 2px;
          right: 4px;
        }

        &::after {
          width: 5px;
          height: 5px;
          top: 18px;
          right: 0;
        }
      }
    }
  }
</style>
