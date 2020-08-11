<template>
  <input
    type="text"
    class="input"
    :value="value"
    v-on:input="$emit('input', $event.target.value)"
    v-on:keyup.enter="$emit('enter')"
  />
</template>

<script>
export default {
  name: 'SinkInput',
  props: {
    value: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
@import './src/assets/colors.scss';

.input {
  width: 100%;
  padding: 8px 10px;
  margin-bottom: 10px;
}

.input:focus {
  outline: none !important;
  border: 1px solid $brink-pink;
  box-shadow: 0 0 10px $cornflower;
}
</style>
