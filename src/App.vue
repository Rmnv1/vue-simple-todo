<template>
  <div id="app">
    <todoFrame/>
  </div>
</template>

<script>
import todoFrame from './components/todoFrame.vue'

export default {
  name: 'Todo',
  components: {
    todoFrame
  }
}
</script>

<style lang="scss">
*{
  box-sizing: border-box;

  // :(
  outline: none; 
}
html {
  height: 100%;
}
body{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: rgb(255,192,192);
  background: linear-gradient(144deg, rgba(255,192,192,1) 0%, rgba(155,112,200,1) 100%);
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
}
</style>
