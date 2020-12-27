<template>
  <div class="todo-create">
    <input type="text" 
           placeholder="Введите задачу" 
           class="todo-create__field"
           v-model="todoText"
           @keypress.enter="createTodo"
          >
    <button @click="createTodo" class="todo-create__btn"></button>
  </div>
</template>
<script>
export default {
  name: 'todoCreate',

  data() {
    return {
      todoText: ''
    }
  },
  methods: {
    createTodo() {
      if (this.todoText.trim()) {
        this.$emit('createTodo', this.todoText)
        this.todoText = ''
      } else {
        alert('Поле не должно быть пустым')
        return false
      }
      // console.log('addTodo', this.todoText);
    }
  },
}
</script>
<style lang="scss">
  .todo-create{
    position: relative;
  }
  .todo-create__field{
    font-family: Avenir, Helvetica, Arial, sans-serif;
    height: 40px;
    font-size: 16px;
    height: 100%;
    width: 100%;
    padding: 15px;
    border: none;
    border-bottom: 1px solid #9b70c8;
    background: #FAFAFA;
    padding-right: 50px;
    font-weight: 300;
    color: #515253;
  }
  .todo-create__btn{
    background: url('../assets/images/enter.svg') no-repeat center;
    background-size: contain;
    height: 28px;
    width: 28px;
    border: none;
    position: absolute;
    right: 10px;
    top: 50%;
    transform: translateY(-50%);
    transform-origin: top;
    cursor: pointer;
    transition: .2s all;
    &:hover{
      transform: scale(1.09) translateY(-50%);
    }
  }
</style>