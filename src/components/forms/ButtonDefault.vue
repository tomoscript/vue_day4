<template>
  <button type="button" @click="handlerClick">{{ title }}</button>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    handlerClick: {
      type: Function,
      required: true,
    },
  },
};
</script>
