/* eslint-disable vue/valid-template-root */
<template>
  <div class="quehacer">
    <p>{{ todo.text }}</p>
    <div class="icons">
      <div @click="$emit('complete', todo.id)">✔️</div>
      <div @click="$emit('remove', todo.id)">🚫</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'QueHacer',
  props: {
    todo: {
      type: Object,
      required: true
    }
  }
}
</script>

<style>
.quehacer {
  display: flex;
}

.icons {
  display: inline-flex;
}
</style>
