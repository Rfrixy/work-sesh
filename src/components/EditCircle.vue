<template>
  <input
    type="number"
    min="0"
    max="99"
    @change="limitVal"
    v-model="numberVal"
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
</style>

<script>
export default {
  mounted() {
    console.log("mounted");
  },
  data() {
    console.log("this props num", this.$props.num);
    return {
      numberVal: this.$props.num,
    };
  },
  props: {
    num: Number,
  },
  methods: {
    limitVal(e) {
      const val = Number.parseInt(e.target.value);
      if (val > 99) val = 99;
      else if (val < 0) val = 0;
      this.numberVal = val;
      this.$emit("update:num", val);
    },
  },
};
</script>
