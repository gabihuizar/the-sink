<template>
  <div class="quehaceres">
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

let nextTodoId = 1

export default {
  name: 'QueHaceres',
  components: {
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
<style>
.quehaceres {
  width: 320px;
  margin: auto;
  background-color: #5d576b;
  color: #fffae3;
}
</style>
