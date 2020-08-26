<template>
  <div>
    <Header></Header>
    <h2>To Study リスト</h2>
    <p>勉強することを以下に記入してください</p>
    <ToDoList></ToDoList>
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import ToDoList from "./components/ToDoList.vue"

export default {
  components:{
    Header,
    ToDoList 
  }
}
</script>
<style scoped>
  h2{
    margin: auto;
    text-align: center;
  }
  p{
    margin: auto;
    text-align: center;
  }
</style>