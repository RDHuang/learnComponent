<template>
  <div>
    <label v-if="label">{{ label }}</label>
    <slot></slot>
    <p style="color: red;" v-if="errorMessage">{{ errorMessage }}</p>
  </div>
</template>

<script>
// element使用的校验插件
import Schame from "async-validator";
export default {
  inject: ["form"],
  data() {
    return {
      errorMessage: "",
    };
  },
  props: {
    label: String,
    prop: String,
  },
  mounted() {
    this.$on("validate", () => {
      this.validate();
    });
  },
  methods: {
    validate() {
      const rules = this.form.rules[this.prop];
      const model = this.form.model[this.prop];
      const desc = { [this.prop]: rules };
      const schame = new Schame(desc);
      return schame.validate({ [this.prop]: model }, (error) => {
        if (error) {
          this.errorMessage = error[0].message;
        } else {
          this.errorMessage = "";
        }
      });
    },
  },
};
</script>

<style>
input {
  margin-top: 20px;
}
</style>
