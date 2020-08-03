<template>
  <div id="app">
    <FatherToChildren />
    <hr>
    <ChildrenToFather></ChildrenToFather>
    <hr>
    <BrotherToBrother></BrotherToBrother>
    <hr>
    <AncestorToPosterity></AncestorToPosterity>
    <hr>
    <br>
    <br>
    <br>
    <br>
    <br>
    <h1>实现el-form组件</h1>

    <ElForm></ElForm>
    <br>
    <br>
    <br>
    <br><br>
    <br>
    <br>
    <br><br>
    <br>
    <br>
    <br><br>
    <br>
    <br>
    <br><br>
    <br>
    <br>
    <br><br>
    <br>
    <br>
    <br><br>
    <br>
    <br>
    <br>
  </div>
</template>

<script>
import FatherToChildren from './components/fatherToChildren/father'
import ChildrenToFather from './components/childrenToFather/father'
import BrotherToBrother from './components/brother'
import AncestorToPosterity from './components/ancestorToPosterity'
import ElForm from './components/form'

export default {
  name: 'App',
  components: {
    FatherToChildren,
    ChildrenToFather,
    BrotherToBrother,
    AncestorToPosterity,
    ElForm
  }
}
</script>
