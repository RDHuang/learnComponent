<template>
  <div>
    <input type="text" :value="value" @input="input" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      value: "",
    };
  },
  methods: {
    input(e) {
      this.$emit("input", e.target.value);
    },
  },
};
</script>
