<template>
  <div>
    <div v-if="msg1">
      <span>子组件</span>
      <p>通过props 传递的值: {{ msg1 }}</p>
    </div>
    
    <div v-if="msg2">
      <span>子组件</span>
      <p>通过引用ref传递的值: {{ msg2 }}</p>
    </div>

    <div v-if="msg3">
      <span>子组件</span>
      <p>通过$children传递的值: {{ msg3 }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    msg1: String,
  },
  data() {
    return {
      msg2: "",
      msg3: "",
    };
  },
};
</script>
