<template>
  <div>
    {{ msg }}
  </div>
</template>

<script>
export default {
  inject: ["ancestor"],
  data() {
    return {
      msg: "",
    };
  },
  mounted() {
    this.msg = this.ancestor.msg;
  },
};
</script>
