# vue组件传值

## 父子传值

* 父 ---> 子

1. 通过props

> 父组件
```
<son msg="传给子组件的值" />
```

> 子组件
```
props: {
    msg: {
        type: String,
        default: ''
    }
}
```

2. 通过引用ref

> 父组件
```
<son ref="son" />
this.$refs.son.msg = "传给子组件的值"
```

> 子组件
```
data() {
    return {
        msg: ''
    }
}
```

3. 通过$children

```
this.$children[0].msg = "传给子组件的值"
```

**tip: 官方文档说明，子元素不能保证顺序（最好不要使用这种，除非只有一个子组件时），同时不是响应式的**

* 子 ---> 父

自定义事件

> 子组件
```
this.$emit('自定义事件名', 传递给伏组件的值)
```

> 父组件
```
<son @子组件自定义事件名="xxx" />

xxx(value) {
    value ===> 为子组件传递过来的数据
}
```

## 兄弟组件传值 (通过共同的父辈或根组件)

```
// $parent(伏组件)  ||  $root(根组件)
this.$parent.$emit('xxx', value)
this.$parent.$on('xxx', (value) => {
    value
})
```

## 祖先和后代之间的传值

> 祖先
```
provide() {
    return {
        xxx: this
    }
}
```

> 后代
```
inject: ['xxx']
```

## 任意组件传值

通过事件总线 $bus 或者 vuex （此处暂时不研究）
