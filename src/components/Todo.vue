<template>
  <h1>{{ msg }}</h1>
  <TodoItem v-model:todoPoints="goalNum" />
  <TodoItem v-model:todoPoints="goalNum" />
  <TodoItem v-model:todoPoints="goalNum" />
  <TodoItem v-model:todoPoints="goalNum" />
  <TodoItem v-model:todoPoints="goalNum" />
</template>

<script>
import EditCircle from "./EditCircle.vue";
import TodoItem from "./TodoItem.vue";
export default {
  name: "Todo",
  props: {
    msg: String,
  },
  data() {
    return {
      count: 0,
      goalNum: 0,
    };
  },
  components: {
    EditCircle,
    TodoItem,
  },
};
</script>
