<template>
  <h1>{{ msg }}</h1>
  <TodoItem
    v-for="(item, index) in todos"
    :key="index"
    v-model:todoItem="todos[index]"
    :deleteTodo="() => deleteTodo(index)"
  />
  <AddButton :addTodo="addTodo" />
</template>

<script>
import EditCircle from "./EditCircle.vue";
import TodoItem from "./TodoItem.vue";
import AddButton from "./AddButton.vue";
export default {
  name: "Todo",
  props: {
    msg: String,
  },
  data() {
    return {
      count: 0,
      goalNum: 0,
      todos: [{ points: 2, text: "Sample todo", completed: false }],
    };
  },
  methods: {
    addTodo() {
      this.todos.push({ points: 0, text: "", completed: false });
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
  components: {
    EditCircle,
    TodoItem,
    AddButton,
  },
};
</script>
