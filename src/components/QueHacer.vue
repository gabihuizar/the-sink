/* eslint-disable vue/valid-template-root */
<template>
  <div class="quehacer">
    <p>{{ todo }}</p>
  </div>
</template>

<script>
export default {
  name: 'QueHacer',
  props: {
    todo: String
  }
}
</script>

<style></style>
