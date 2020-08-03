<template>
  <div>
    <h2>父组件给子组件传值</h2>
    <div>
      <div>
        <input v-model="data1" />
      </div>
      <Children :msg1="data1" />
    </div>
    <div>
      <div>
        <input v-model="data2" @input="input(data2)" />
      </div>
      <Children ref="children" />
    </div>

    <div>
      <div>
        <input v-model="data3" @input="input2(data3)" />
      </div>
      <Children />
    </div>
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
      data1: "数据一",
      data2: "数据二",
      data3: "数据三",
    };
  },
  mounted() {
    this.$refs.children.msg2 = this.data2;
    this.$children[2].msg3 = this.data3;
  },
  methods: {
    input(val) {
      this.$refs.children.msg2 = val;
    },
    input2(val) {
      this.$children[2].msg3 = val;
    },
  },
};
</script>

<style lang="scss" scoped></style>
