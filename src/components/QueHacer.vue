/* eslint-disable vue/valid-template-root */
<template>
  <div class="quehacer">
    <p>{{ todo.text }}</p>
    <div class="icons">
      <div v-on:click="toggleComplete">
        <img
          v-if="!complete"
          src="../assets/check_box_outline_blank-24px.svg"
        />
        <img v-else src="../assets/check_box-24px.svg" />
      </div>
      <div @click="$emit('remove', todo.id)">
        <img src="../assets/clear-24px.svg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'QueHacer',
  data: () => {
    return {
      complete: false
    }
  },
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    toggleComplete() {
      this.complete = !this.complete
    }
  }
}
</script>

<style>
.quehacer {
  display: flex;
  justify-content: space-between;
}

.icons {
  display: inline-flex;
  cursor: pointer;
  align-items: center;
}
</style>
