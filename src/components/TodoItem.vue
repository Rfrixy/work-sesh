<template>
  <div class="wrapper">
    <div class="todo-item">
      <EditCircle v-model:num="points" :completed="completed" />
      <input type="checkbox" class="todo-checkbox" v-model="completed" />
      <input type="text" v-model="text" :class="{ strikethrough: completed }" />
      <button type="button" class="trash-button" @click="deleteTodo">
        <i class="trash-icon fa fa-trash-o"></i>
      </button>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  padding-top: 18px;
  display: flex;
  justify-content: center;
}

.todo-item {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 12px;
  width: 100%;
  max-width: 550px;
}

.todo-checkbox {
  margin-left: 12px;
  height: 18px;
  width: 18px;
  vertical-align: middle;
}

.strikethrough {
  text-decoration: line-through;
}

input[type="text"] {
  /* border-radius: 25px; */
  margin-left: 12px;
  border: 1px solid #e3e3e3;
  height: 2em;
  border-left: none;
  border-right: none;
  line-height: 1em;
  text-align: left;
  border-top: none;
  width: fit-content;
  min-width: 15px;
  padding: 4px;
  padding-left: 12px;
  margin-right: 12px;
  flex: 1;
}

input:focus {
  outline: none;
}

/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type="number"] {
  -moz-appearance: textfield;
}

.trash-button {
  border: none;
  background-color: transparent;
  outline: none;
  cursor: pointer;
  color: #999;
  padding: 8px;
  vertical-align: middle;
}

.trash-icon {
  font-size: 18px;
}
</style>

<script>
import EditCircle from "./EditCircle.vue";

export default {
  data() {
    console.log("this props ", this.$props.todoItem);
    return {
      points: this.$props.todoItem.points,
      text: this.$props.todoItem.text,
      completed: this.$props.todoItem.completed,
    };
  },
  watch: {
    points() {
      this.emitUpdate();
    },
    text() {
      this.emitUpdate();
    },
    completed() {
      this.emitUpdate();
    },
  },
  methods: {
    emitUpdate() {
      this.$emit("update:todoItem", {
        points: this.points,
        text: this.text,
        completed: this.completed,
      });
    },
  },
  props: {
    todoItem: Object,
    deleteTodo: Function,
  },
  components: {
    EditCircle,
  },
};
</script>
