<template>
  <div class="quehaceres">
    <SinkInput
      v-model="newTodoText"
      placeholder="Nuevo que hacer"
      @enter="addToDo"
    />
    <SinkButton text="Add Que Hacer" @clicked="addToDo" />
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
import SinkInput from '@/components/SinkInput.vue'
import SinkButton from '@/components/SinkButton.vue'

let nextTodoId = 1

export default {
  name: 'QueHaceres',
  components: {
    SinkInput,
    SinkButton,
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
    addToDo() {
      const trimmedText = this.newTodoText.trim()
      if (trimmedText) {
        this.todos.push({
          id: nextTodoId++,
          text: trimmedText
        })
        this.newTodoText = ''
      }
    },
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
