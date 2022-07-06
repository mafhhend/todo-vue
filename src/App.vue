<template>

  <div class="wrapper">
    <i-todo @addTodo="addTodo" />
    <f-todo @changeTab="changeTab" @clearTodos="clearTodos" />
    <l-todo @toggleComplete="toggleComplete" :tab="tab" :todos="todos" />
  </div>

</template>


<script>
import FilterTodoVue from './components/FilterTodo.vue'
import InputTodoVue from './components/InputTodo.vue'
import ListTodoVue from './components/ListTodo.vue'
export default {
  data() {
    return {
      todos: [],
      tab: 'all'
    }
  },
  components: {
    "iTodo": InputTodoVue,
    "fTodo": FilterTodoVue,
    "lTodo": ListTodoVue
  },

  methods: {
    addTodo(inputText) {
      this.todos.push(inputText)
    },

    clearTodos() {
      this.todos = []
    },
    toggleComplete(id) {
      this.todos = this.todos.map(todo => {
        if (todo.id === id) {
          todo.complete = !todo.complete
        }
        return todo;
      })
    },
    changeTab(value) {
      this.tab = value
    }
  }
}
</script>