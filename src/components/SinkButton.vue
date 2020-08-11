<template>
  <button class="sink-button" v-on:click="$emit('clicked')">{{ text }}</button>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
@import './src/assets/colors.scss';

.sink-button {
  padding: 10px 10px;
  background-color: $brink-pink;
  color: $cornflower;
  border: none;
  cursor: pointer;
}
</style>
