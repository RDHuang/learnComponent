<template>
  <div>
    <h2>兄弟之间传值</h2>
    <h3>我是兄弟一</h3>
    <div><button @click="toBrother">点击传值给兄弟二</button></div>
  </div>
</template>

<script>
export default {
  methods: {
    toBrother() {
      this.$parent.$emit("method", "我传给我兄弟的值");
    },
  },
};
</script>
