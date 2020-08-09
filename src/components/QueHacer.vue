/* eslint-disable vue/valid-template-root */
<template>
  <div class="queHacer">
    <p>{{ todo.text }}</p>
    <div class="icons">
      <div v-on:click="toggleComplete">
        <svg
          v-if="!complete"
          xmlns="http://www.w3.org/2000/svg"
          height="24"
          viewBox="0 0 24 24"
          width="24"
        >
          <path d="M0 0h24v24H0V0z" fill="none" />
          <path
            d="M19 5v14H5V5h14m0-2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2z"
          />
        </svg>
        <svg
          v-else
          xmlns="http://www.w3.org/2000/svg"
          height="24"
          viewBox="0 0 24 24"
          width="24"
        >
          <path d="M0 0h24v24H0V0z" fill="none" />
          <path
            d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 16H5V5h14v14zM17.99 9l-1.41-1.42-6.59 6.59-2.58-2.57-1.42 1.41 4 3.99z"
          />
        </svg>
      </div>
      <div @click="$emit('remove', todo.id)">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          height="24"
          viewBox="0 0 24 24"
          width="24"
        >
          <path d="M0 0h24v24H0V0z" fill="none" />
          <path
            d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12 19 6.41z"
          />
        </svg>
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

<style lang="scss" scoped>
@import './src/assets/colors.scss';

.queHacer {
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
}

.icons {
  display: inline-flex;
  cursor: pointer;
  align-items: center;
}

svg {
  fill: $cornflower;
}
</style>
