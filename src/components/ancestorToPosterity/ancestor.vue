<template>
  <div>
    <p>我是老祖宗</p>
    <slot></slot>
  </div>
</template>

<script>
export default {
  provide() {
    return {
      ancestor: this,
    };
  },
  data() {
    return {
      msg: "老祖宗给我们儿孙后代们说的话",
    };
  },
};
</script>
