<template>
  <div class="todo-list">
    <h1 class="todo-list__title">Список задач:</h1>
    <div class="todo-list__info" v-if="!todos.length">
      <span class="todo-list__info-text">На данный момент список задач пуст!</span>
      <span class="todo-list__info-text">Вы можете добавить что-то</span>
    </div>
    <todoItem v-for="todo in todos" 
              :key="todo.id"
              :todo="todo"
              @removeTodo="removeItem"
              v-else
              />
  </div>
</template>
<script>
import todoItem from './todoItem'

export default {
  name: 'todoList',
  components: {
    todoItem
  },
  props: [
    'todoText'
  ],
  data() {
    return {
      currentId: 3,
      todos: [
      ]
    }
  },
  watch: {
    todoText: function(val) {
        this.todos.push({
        id: this.currentId,
        title: this.todoText,
        completed: false
      })
      this.currentId++
    }
  },
  computed: {
  },
  methods: {
    removeItem(data){
      const index = this.todos.findIndex(item => item.id == data)
      this.todos.splice(index, 1)
    }
  },
}
</script>
<style lang="scss">
  .todo-list{
    height: 100%;
    position: relative;
    overflow-y: scroll;
  }
  .todo-list__info{
    width: 100%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  .todo-list__info-text{
    display: block;
    text-align: center;
    margin-bottom: 10px;
    margin-top: 10px;
    color: #515253;
  }
  .todo-list__title{
    font-size: 22px;
    text-align: center;
    font-weight: 300;
    margin-top: 25px;
  }
</style>