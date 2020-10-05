<template>
  <div class="wrapper">
    <EditCircle v-model:num="numberVal" />
    <span class="todo-item">
      <input type="checkbox" class="todo-checkbox" />
      <input type="text" />
      <button type="button" class="trash-button">
        <i class="trash-icon fa fa-trash-o"></i>
      </button>
    </span>
  </div>
</template>

<style scoped>
.wrapper {
  padding-top: 18px;
}

.todo-item {
  display: inline-block;
  margin-left: 12px;
}

.todo-checkbox {
  margin-left: 12px;
  height: 18px;
  width: 18px;
  vertical-align: middle;
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
  width: 400px;
  padding: 4px;
  padding-left: 12px;
  margin-right: 12px;
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
    console.log("this props num", this.$props.num);
    return {
      numberVal: this.$props.todoPoints,
    };
  },
  props: {
    todoPoints: Number,
  },
  components: {
    EditCircle,
  },
};
</script>
