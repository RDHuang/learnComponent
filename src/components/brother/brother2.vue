<template>
  <div>
    <h2>兄弟之间传值</h2>

    <h3>我是兄弟二</h3>

    <div>我接收我兄弟的值：{{ msg }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "",
    };
  },
  mounted() {
    this.$parent.$on("method", (msg) => {
      this.msg = msg;
    });
  },
};
</script>
