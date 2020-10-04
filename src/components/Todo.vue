<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>Edit <code>components/Todo.vue</code> to test hot module replacement.</p>
  <EditCircle />
</template>

<script>
import EditCircle from "./EditCircle.vue";
export default {
  name: "Todo",
  props: {
    msg: String,
  },
  data() {
    return {
      count: 0,
    };
  },
  components: {
    EditCircle,
  },
};
</script>
