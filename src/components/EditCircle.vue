<template>
  <input
    type="number"
    min="0"
    max="99"
    value="0"
    @change="(v) => console.log(v)"
  />
</template>

<style scoped>
input {
  border-radius: 25px;
  border: 2px solid #73ad21;
  height: 2em;
  line-height: 1em;
  width: 25px;
  text-align: center;
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
</style>

<script>
export default {
  mounted() {
    console.log("mounted");
  },
};
</script>
