<template>
  <div>
    <button type="button" class="add-button" @click="addTodo">
      + Add todo
    </button>
  </div>
</template>

<style scoped>
.add-button {
  padding: 4px;
  padding-left: 16px;
  padding-right: 16px;
  border-radius: 12px;
  margin: 12px;
  margin-top: 24px;
  cursor: pointer;
  background-color: #fff;
  border: 2px solid #ddd;
  outline: none;
}

.add-button:hover {
  background-color: #e3e3e3;
}
</style>

<script>
export default {
  props: {
    addTodo: Function,
  },
};
</script>
