<template>
  <div>
    <h2>子组件给父组件传值</h2>
    <Children @input="input"></Children>
    <div>子组件传过来的值：{{ value }}</div>
  </div>
</template>

<script>
import Children from "./children";
export default {
  components: {
    Children,
  },
  data() {
    return {
      value: "",
    };
  },
  methods: {
    input(val) {
      this.value = val;
    },
  },
};
</script>
