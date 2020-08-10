<template>
  <div class="queHacerInput">
    <input
      type="text"
      class="input"
      :value="value"
      placeholder="Nuevo que hacer"
    />
    <button>Add Que Hacer</button>
  </div>
</template>

<script>
export default {
  name: 'QueHacerInput',
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

.queHacerInput {
  margin-bottom: 10px;
}

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

button {
  padding: 10px 10px;
  background-color: $brink-pink;
  color: $cornflower;
  border: none;
  cursor: pointer;
}
</style>
