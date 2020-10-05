<template>
  <input
    type="number"
    min="0"
    max="99"
    @change="limitVal"
    v-model="numberVal"
    @focus="$event.target.select()"
    :class="{ green: completed }"
  />
</template>

<style scoped>
input {
  border-radius: 25px;
  border: 2px solid #d3d3d3;
  height: 2em;
  line-height: 1em;
  width: 25px;
  text-align: center;
  border-top: none;
  border-bottom: none;
}

.green {
  border: 2px solid #73ad2181;
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
  data() {
    console.log("this props num", this.$props.num);
    return {
      numberVal: this.$props.num,
    };
  },
  props: {
    num: Number,
    completed: Boolean,
  },
  methods: {
    limitVal(e) {
      let val = Number.parseInt(e.target.value);
      if (val > 99) val = 99;
      else if (val < 0) val = 0;
      this.numberVal = val;
      this.$emit("update:num", val);
    },
  },
};
</script>
