<template>
  <div class="frame">
    <todoCreate @createTodo="addTodo"/>
    <todoList :todoText="todoText"/>
  </div>
</template>
<script>
import todoCreate from './todoCreate'
import todoList from './todoList'

export default {
  name: 'todoFrame',
  components: {
    todoCreate, todoList
  },
  data() {
    return {
      todoText: ''
    }
  },
  methods: {
    addTodo(data) {
      this.todoText = data
    }
  },
}
</script>
<style lang="scss">
  .frame{
    width: 100%;
    height: 100%;
    max-width: 450px;
    max-height: 77vh;
    border-radius: 15px;
    background: #FAFAFA;
    display: flex;
    flex-direction: column;
    // justify-content: space-between;
    padding: 15px;
    margin: 0 10px;
  }
</style>