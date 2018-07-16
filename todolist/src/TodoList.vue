//规范：在组件里不允许使用双引号,使用括号和大括号要有空格如data () {},handleSumit()里换行不能加逗号

<template>
  <div>
    <input v-model="inputValue"/>
    <button @click="handleSubmit">提交</button>
    <div>
      <todo-item v-for="(item,index) of list"
      :key="index"
      :content="item"
      :index="index"
      @delete="handleDelete"
      ></todo-item>
    </div>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  components: {
    'todo-item': TodoItem
  },
  data () {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit () {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete (index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>
</style>
