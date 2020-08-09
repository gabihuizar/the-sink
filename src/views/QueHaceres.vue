<template>
  <div class="quehaceres">
    <QueHacerInput ßv-model="newTodoText" />
    <QueHacer
      v-for="todo in todos"
      :key="todo.id"
      :todo="todo"
      @remove="removeToDo"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import QueHacer from '@/components/QueHacer.vue'
import QueHacerInput from '@/components/QueHacerInput.vue'

let nextTodoId = 1

export default {
  name: 'QueHaceres',
  components: {
    QueHacerInput,
    QueHacer
  },
  data: () => {
    return {
      newTodoText: '',
      todos: [
        {
          id: nextTodoId++,
          text: 'go to lowes'
        },
        {
          id: nextTodoId++,
          text: 'Learn about single-file components'
        },
        {
          id: nextTodoId++,
          text: 'mop & sweep'
        }
      ]
    }
  },
  methods: {
    addToDo() {},
    removeToDo(id) {
      this.todos = this.todos.filter(todo => {
        return todo.id !== id
      })
    }
  }
}
</script>
<style lang="scss" scoped>
@import './src/assets/colors.scss';

.quehaceres {
  width: 320px;
  margin: auto;
  background-color: $dark-purple-grey;
  color: $cornflower;
}
</style>
