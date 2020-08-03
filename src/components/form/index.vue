<template>
  <el-form :model="form" :rules="rules" ref="form">
    <el-form-item label="用户名" prop="username">
      <el-input v-model="form.username"></el-input>
    </el-form-item>
    <el-form-item label="密码" prop="password">
      <el-input type="password" v-model="form.password"></el-input>
    </el-form-item>
    <el-form-item>
      <button @click="login">登录</button>
    </el-form-item>
  </el-form>
</template>

<script>
import ElForm from "./el-form";
import ElFormItem from "./el-form-item";
import ElInput from "./el-input";
export default {
  components: {
    ElForm,
    ElFormItem,
    ElInput,
  },
  data() {
    return {
      form: {
        username: "",
        password: "",
      },
      rules: {
        username: [{ required: true, message: "请输入用户名" }],
        password: [{ required: true, message: "请输入密码" }],
      },
    };
  },
  methods: {
    login() {
      this.$refs.form.validate((isValid) => {
        if (isValid) {
          alert("登录成功");
        } else {
          alert("登录失败");
        }
      });
    },
  },
};
</script>
