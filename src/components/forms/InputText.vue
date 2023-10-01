<template>
  <input v-model="internalValue" />
</template>

<script>
export default {
  props: {
    value: String,
  },
  data() {
    return {
      internalValue: this.value,
    };
  },
  watch: {
    internalValue(newVal) {
      this.$emit("input", newVal);
    },
    value(newVal) {
      this.internalValue = newVal;
    },
  },
};
</script>
