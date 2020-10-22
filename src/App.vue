<template>
  <div class="todo-container">
    <div class="todo-wrap">
      <Header :addTodo = "addTodo"></Header>
      <List :todos="todos" 
      :updateTodo="updateTodo"
      :deleteTodo="deleteTodo"></List>
      <Footer :todos="todos"></Footer>
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header";
import List from "@/components/List";
import Footer from "@/components/Footer";
export default {
  name: "",
  components: {
    Header,
    List,
    Footer,
  },
  data() {
    return {
      todos: [
        { id: 1, content: "房子", isOver: true },
        { id: 2, content: "狗子", isOver: false },
        { id: 3, content: "车子", isOver: false },
        { id: 4, content: "花园", isOver: false },
      ],
    };
  },
  methods:{
    addTodo(todo){
      this.todos.unshift(todo)
    },
    updateTodo(index){
      this.todos[index].isOver=!this.todos[index].isOver
    },
    deleteTodo(index){
      this.todos.splice(index,1)
    }
  }
};
</script>

<style scoped>
.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>